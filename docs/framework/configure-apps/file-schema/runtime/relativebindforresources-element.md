---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51129f9bb3a278d32a5da723dcc339f5e918c0f4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289808"
---
# <a name="relativebindforresources-element"></a>\<RelativeBindForResources >-Element
Optimiert den Test für Satellitenassemblys.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<RelativeBindForResources >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die common Language Runtime die Überprüfung auf Satellitenassemblys optimiert.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Runtime wird den Test für Satellitenassemblys nicht optimiert werden. Dies ist der Standardwert.|  
|`true`|Die Laufzeit optimiert den Test für Satellitenassemblys.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Im Allgemeinen Resource Manager-Tests für Ressourcen, wie in der [Packaging and Deploying Resources](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md) Thema. Dies bedeutet, dass bei der Ressourcen-Manager für eine bestimmte lokalisierte Version einer Ressource Tests, möglicherweise suchen Sie im globalen Assemblycache, Satellitenassemblys in einem kulturspezifischen Ordner, in der Anwendung Code-Basis, Abfrage Windows Installer gesucht und Auslösen der <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis. Die `<relativeBindForResources>` Element optimiert die Möglichkeit, die in der Resource Manager-für Satellitenassemblys Tests. Sie können die Leistung verbessert, wenn der Testvorgang für Ressourcen in den folgenden Situationen:  
  
-   Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird. Das heißt, wenn die Code-Assembly im globalen Assemblycache installiert ist, müssen die Satellitenassemblys auch dort installiert werden. Wenn die Codeassembly in die Codebasis der Anwendung installiert ist, müssen auch die Satellitenassemblys in einem kulturspezifischen Ordner, in der Codebasis installiert werden.  
  
-   Wenn Windows Installer nicht verwendet wird oder nur selten verwendet für die Installation von Satellitenassemblys bei Bedarf.  
  
-   Wenn Anwendungscode behandelt nicht das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis.  
  
 Festlegen der `enabled` Attribut der `<relativeBindForResources>` Element `true` optimiert die Resource Manager Test für Satellitenassemblys wie folgt:  
  
-   Er verwendet den Speicherort der übergeordneten Codeassembly, um für die Satellitenassembly zu testen.  
  
-   Er fragt Windows Installer nicht für Satellitenassemblys.  
  
-   Sie löst nicht die <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis.  
  
## <a name="see-also"></a>Siehe auch
- [Verpacken und Bereitstellen von Ressourcen](../../../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
