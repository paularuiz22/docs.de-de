---
title: Plattformübergreifende Ziele für .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Erstellen von plattformübergreifenden .NET Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 6bd310f2e4b7a9bd7bb550ed9c7da9ebabdf64ba
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129713"
---
# <a name="cross-platform-targeting"></a>Plattformübergreifende Ziele

Modernes .NET unterstützt mehrere Betriebssysteme und Geräte. Es ist wichtig, dass .NET-Open-Source-Bibliotheken so viele Entwickler wie möglich unterstützen, unabhängig davon, ob sie eine in Azure gehostete ASP.NET-Website oder ein .NET-Spiel in Unity erstellen.

## <a name="net-standard"></a>.NET-Standard

.NET Standard ist die beste Möglichkeit, plattformübergreifenden Support zu einer .NET-Bibliothek hinzuzufügen. [.NET Standard](../net-standard.md) ist eine Spezifikation von .NET-APIs, die für alle .NET-Implementierungen verfügbar sind. Mit dem Targeting von .NET Standard können Sie Bibliotheken erstellen, die nur APIs verwenden dürfen, die sich in einer bestimmten Version von .NET Standard befinden. Das bedeutet, dass es von allen Plattformen verwendet werden kann, die diese Version von .NET Standard implementieren.

![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")

Das Targeting von .NET Standard und die erfolgreiche Kompilierung Ihres Projekts garantieren nicht, dass die Bibliothek auf allen Plattformen erfolgreich läuft:

1. Bei plattformspezifischen APIs tritt auf anderen Plattformen ein Fehler auf. Beispielsweise wird <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> unter Windows erfolgreich ausgeführt, gibt jedoch unter anderen Betriebssystemen <xref:System.PlatformNotSupportedException> aus.
2. APIs können sich unterschiedlich verhalten. Beispielsweise haben Reflektions-APIs unterschiedliche Leistungsmerkmale, wenn eine Anwendung eine Ahead-of-time-Kompilierung auf iOS oder UWP verwendet.

> [!TIP]
> Das .NET-Team [bietet ein Roslyn-Analysetool](../analyzers/api-analyzer.md) zur Erkennung möglicher Probleme.

**✔️ DO** Beginnen Sie, indem Sie ein `netstandard2.0`-Ziel einschließen.

> Die meisten Bibliotheken für allgemeine Zwecke sollte außerhalb von .NET Standard 2.0 keine APIs erfordern. .NET Standard 2.0 wird von allen modernen Plattformen unterstützt und ist der empfohlene Weg, um mehrere Plattformen mit einem Ziel zu unterstützen.

**❌ VERMEIDEN** Sie ein `netstandard1.x`-Ziel.

> .NET Standard 1.x wird als ein granularer Satz von NuGet-Paketen verteilt, der ein großes Abhängigkeitsdiagramm erstellt und dazu führt, dass Entwickler beim Erstellen viele Pakete herunterladen. Moderne .NET-Plattformen, einschließlich .NET Framework 4.6.1, UWP und Xamarin unterstützen .NET Standard 2.0. Sie sollten.NET Standard 1.x nur dann als Ziel verwenden, wenn Sie speziell auf eine ältere Plattform abzielen müssen.

**✔️ DO** Schließen Sie ein `netstandard2.0`-Ziel ein, wenn Sie ein `netstandard1.x`-Ziel benötigen.

> Alle Plattformen, die .NET Standard 2.0 unterstützen, verwenden das `netstandard2.0`-Ziel und profitieren von einem kleineren Paketdiagramm, während ältere Plattformen noch funktionieren und auf die Verwendung des `netstandard1.x`-Ziels zurückgreifen.

**❌ DON‘T** Fügen Sie kein .NET Standard-Ziel ein, wenn die Bibliothek auf einem plattformspezifischen Appmodell basiert.

> Beispielsweise hängt eine Bibliothek eines UWP-Steuerelemente-Toolkit von einem Appmodell ab, das nur in UWP verfügbar ist. Appmodell-spezifische APIs sind nicht in .NET Standard verfügbar.

## <a name="multi-targeting"></a>Festlegung von Zielversionen

Manchmal müssen über Ihre Bibliotheken auf Framework-spezifische APIs zugreifen. Der beste Weg, Framework-spezifische APIs aufzurufen, ist die Verwendung der Festlegung von Zielversionen, das Ihr Projekt für viele [.NET-Zielframeworks](../frameworks.md) und nicht nur für eines erstellt.

Um Ihre Kunden davor zu schützen, Bibliotheken für einzelne Frameworks erstellen zu müssen, sollten Sie eine .NET Standard-Ausgabe sowie eine oder mehrere Framework-spezifische Ausgaben anstreben. Bei der Festlegung von Zielversionen werden alle Assemblys in einem einzigen NuGet-Paket verpackt. Die Benutzer können dann auf das gleiche Paket zurückgreifen, und NuGet wählt die passende Implementierung aus. Ihre .NET Standard-Bibliothek dient als Fallbackbibliothek, die überall verwendet wird, mit Ausnahme der Fälle, in denen Ihr NuGet-Paket eine Framework-spezifische Implementierung bietet. Die Festlegung von Zielversionen ermöglicht es Ihnen, die bedingte Kompilierung in Ihrem Code zu verwenden und Framework-spezifische APIs aufzurufen.

![NuGet-Paket mit mehreren Assemblys](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet-Paket mit mehreren Assemblys")

**✔️ ERWÄGEN.** Sie das Targeting von .NET-Implementierungen zusätzlich zu .NET Standard.

> Das Targeting von .NET-Implementierungen ermöglichen es Ihnen, plattformspezifische APIs aufzurufen, die sich außerhalb von .NET-Standard befinden.
>
> Dabei muss weiterhin der Support für .NET Standard gewährleistet sein. Lösen Sie sich stattdessen von der Implementierung und bieten Sie Funktions-APIs. Auf diese Weise kann Ihre Bibliothek überall verwendet werden und unterstützt die Runtimehervorhebung von Funktionen.

**❌ Vermeiden** Sie das Festlegen von mehreren Zielen sowie das Verwenden von .NET Standard als Ziel, wenn Ihr Quellcode für alle Ziele identisch ist.

> Die .NET Standard-Assembly wird von NuGet automatisch verwendet. Das Targeting einzelner .NET-Implementierungen erhöht die `*.nupkg`-Größe, ohne dass sich daraus Vorteil ergeben.

**✔️ ERWÄGEN** Sie, ein Ziel für `net461` hinzuzufügen, wenn Sie ein `netstandard2.0`-Ziel anbieten. 

> Bei der Verwendung von .NET Standard 2.0 aus .NET Framework gibt es einige Probleme, die in .NET Framework 4.7.2 behoben wurden. Sie können das Erlebnis für Entwickler, die noch mit .NET Framework 4.6.1 bis 4.7.1 arbeiten, verbessern, indem Sie ihnen eine Binärdatei anbieten, die für .NET Framework 4.6.1 erstellt wurde.

**✔️ DO** Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.

> NuGet wählt das beste Ziel für den Entwickler aus und schützt ihn davor, die passende Implementierung auswählen zu müssen.

**✔️ DO** Verwenden Sie bei der Festlegung von Zielversionen die `TargetFrameworks`-Eigenschaft der Projektdatei.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**✔ ERWÄGEN** Sie bei der Festlegung von Zielversionen für UWP und Xamarin die Verwendung von [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras), da es Ihre Projektdatei stark vereinfacht.

## <a name="older-targets"></a>Ältere Ziele

.NET unterstützt die Festlegung von Versionen des .NET Frameworks, die seit langem nicht mehr unterstützt werden, sowie Plattformen, die selten verwendet werden. Es ist zwar sinnvoll, Ihre Bibliothek mit so vielen Zielen wie möglich arbeiten zu lassen, aber die Notwendigkeit, fehlende APIs zu umgehen, kann zu einem erheblichen Aufwand führen. Wir glauben, dass bestimmte Frameworks angesichts ihrer Reichweite und Grenzen nicht mehr als Ziel genutzt werden sollten.

**❌ DON‘T** Schließen Sie keine portable Klassenbibliothek (PCL) als Ziel ein. Beispielsweise `portable-net45+win8+wpa81+wp8`.

> .NET Standard ist die moderne Möglichkeit, um plattformübergreifende .NET-Bibliotheken zu unterstützen und ist der Ersatz für PCLs.

**❌ DON‘T** Schließen Sie keine Ziele für .NET-Plattformen ein, die nicht mehr unterstützt werden. Platzhalter in einer derartigen Schreibweise sind z.B. `SL4` und `WP`.

>[!div class="step-by-step"]
>[Zurück](get-started.md)
>[Weiter](strong-naming.md)
