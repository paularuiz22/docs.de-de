---
title: Klassen und Objekte – Tutorial zur Einführung in C#
description: Erstellen Ihres ersten C#-Programms und Erforschen objektorientierter Konzepte
ms.date: 10/11/2017
ms.custom: mvc
ms.openlocfilehash: 8b823e05ea5e51bb3096d6a0611630c996f56b33
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50205361"
---
# <a name="explore-object-oriented-programming-with-classes-and-objects"></a><span data-ttu-id="bed78-103">Erkunden der objektorientierten Programmierung mit Klassen und Objekten</span><span class="sxs-lookup"><span data-stu-id="bed78-103">Explore object oriented programming with classes and objects</span></span>

<span data-ttu-id="bed78-104">Für dieses Tutorial wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="bed78-104">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="bed78-105">Das .NET-Thema [Erste Schritte in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-PC.</span><span class="sxs-lookup"><span data-stu-id="bed78-105">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="bed78-106">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie im Artikel [Einführung in Entwicklungstools](local-environment.md), der Links zu weiteren Ressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="bed78-106">A quick overview of the commands you'll use is in the [Become familiar with the development tools](local-environment.md) with links to more details.</span></span>

## <a name="create-your-application"></a><span data-ttu-id="bed78-107">Erstellen Ihrer Anwendung</span><span class="sxs-lookup"><span data-stu-id="bed78-107">Create your application</span></span>

<span data-ttu-id="bed78-108">Erstellen Sie in einem Terminalfenster ein Verzeichnis namens **classes**.</span><span class="sxs-lookup"><span data-stu-id="bed78-108">Using a terminal window, create a directory named **classes**.</span></span> <span data-ttu-id="bed78-109">Dort werden Sie Ihre Anwendung erstellen.</span><span class="sxs-lookup"><span data-stu-id="bed78-109">You'll build your application there.</span></span> <span data-ttu-id="bed78-110">Wechseln Sie in dieses Verzeichnis, und geben Sie `dotnet new console` im Konsolenfenster ein.</span><span class="sxs-lookup"><span data-stu-id="bed78-110">Change to that directory and type `dotnet new console` in the console window.</span></span> <span data-ttu-id="bed78-111">Dieser Befehl erstellt die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bed78-111">This command creates your application.</span></span> <span data-ttu-id="bed78-112">Öffnen Sie **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="bed78-112">Open **Program.cs**.</span></span> <span data-ttu-id="bed78-113">Es sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bed78-113">It should look like this:</span></span>

```csharp
using System;

namespace classes
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="bed78-114">In diesem Tutorial erstellen Sie neue Typen, die ein Bankkonto darstellen.</span><span class="sxs-lookup"><span data-stu-id="bed78-114">In this tutorial, you're going to create new types that represent a bank account.</span></span> <span data-ttu-id="bed78-115">Entwickler definieren jede Klasse in der Regel in einer anderen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="bed78-115">Typically developers define each class in a different text file.</span></span> <span data-ttu-id="bed78-116">Dies erleichtert die Verwaltung bei zunehmender Programmgröße.</span><span class="sxs-lookup"><span data-stu-id="bed78-116">That makes it easier to manage as a program grows in size.</span></span>  <span data-ttu-id="bed78-117">Erstellen Sie eine neue Datei mit dem Namen **BankAccount.cs** im Verzeichnis **classes**.</span><span class="sxs-lookup"><span data-stu-id="bed78-117">Create a new file named **BankAccount.cs** in the **classes** directory.</span></span> 

<span data-ttu-id="bed78-118">Diese Datei enthält die Definition eines ***Bankkontos***.</span><span class="sxs-lookup"><span data-stu-id="bed78-118">This file will contain the definition of a ***bank account***.</span></span> <span data-ttu-id="bed78-119">In der objektorientierten Programmierung wird der Code organisiert, indem Typen in Form von ***Klassen*** erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bed78-119">Object Oriented programming organizes code by creating types in the form of ***classes***.</span></span> <span data-ttu-id="bed78-120">Diese Klassen enthalten den Code, der eine bestimmte Entität darstellt.</span><span class="sxs-lookup"><span data-stu-id="bed78-120">These classes contain the code that represents a specific entity.</span></span> <span data-ttu-id="bed78-121">Die `BankAccount`-Klasse stellt ein Bankkonto dar.</span><span class="sxs-lookup"><span data-stu-id="bed78-121">The `BankAccount` class represents a bank account.</span></span> <span data-ttu-id="bed78-122">Der Code implementiert bestimmte Vorgänge mittels Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bed78-122">The code implements specific operations through methods and properties.</span></span> <span data-ttu-id="bed78-123">In diesem Tutorial unterstützt das Bankkonto dieses Verhalten:</span><span class="sxs-lookup"><span data-stu-id="bed78-123">In this tutorial, the bank account supports this behavior:</span></span>

1. <span data-ttu-id="bed78-124">Es enthält eine 10-stellige Zahl, die das Bankkonto eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="bed78-124">It has a 10-digit number that uniquely identifies the bank account.</span></span>
1. <span data-ttu-id="bed78-125">Es enthält eine Zeichenfolge, die den bzw. die Namen des Besitzers speichert.</span><span class="sxs-lookup"><span data-stu-id="bed78-125">It has a string that stores the name or names of the owners.</span></span>
1. <span data-ttu-id="bed78-126">Der Kontostand kann abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bed78-126">The balance can be retrieved.</span></span>
1. <span data-ttu-id="bed78-127">Es akzeptiert Einzahlungen.</span><span class="sxs-lookup"><span data-stu-id="bed78-127">It accepts deposits.</span></span>
1. <span data-ttu-id="bed78-128">Es akzeptiert Abbuchungen.</span><span class="sxs-lookup"><span data-stu-id="bed78-128">It accepts withdrawals.</span></span>
1. <span data-ttu-id="bed78-129">Der anfängliche Kontostand muss positiv sein.</span><span class="sxs-lookup"><span data-stu-id="bed78-129">The initial balance must be positive.</span></span>
1. <span data-ttu-id="bed78-130">Abbuchungen dürfen nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-130">Withdrawals cannot result in a negative balance.</span></span>

## <a name="define-the-bank-account-type"></a><span data-ttu-id="bed78-131">Definieren des Bankkontotyps</span><span class="sxs-lookup"><span data-stu-id="bed78-131">Define the bank account type</span></span>

<span data-ttu-id="bed78-132">Sie können beginnen, indem Sie die Grundlagen einer Klasse erstellen, die dieses Verhalten definiert.</span><span class="sxs-lookup"><span data-stu-id="bed78-132">You can start by creating the basics of a class that defines that behavior.</span></span> <span data-ttu-id="bed78-133">Die sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bed78-133">It would look like this:</span></span>

```csharp
using System;

namespace classes
{
    public class BankAccount
    {
        public string Number { get; }
        public string Owner { get; set; }
        public decimal Balance { get; }

        public void MakeDeposit(decimal amount, DateTime date, string note)
        {
        }

        public void MakeWithdrawal(decimal amount, DateTime date, string note)
        {
        }
    }
}
```

<span data-ttu-id="bed78-134">Bevor wir fortfahren, lassen Sie uns anschauen, was Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bed78-134">Before going on, let's take a look at what you've built.</span></span>  <span data-ttu-id="bed78-135">Die `namespace`-Deklaration ist eine Möglichkeit, Ihren Code logisch zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-135">The `namespace` declaration provides a way to logically organize your code.</span></span> <span data-ttu-id="bed78-136">Da dieses Tutorial relativ klein ist, platzieren Sie den gesamten Code in einen einzigen Namespace.</span><span class="sxs-lookup"><span data-stu-id="bed78-136">This tutorial is relatively small, so you'll put all the code in one namespace.</span></span> 

<span data-ttu-id="bed78-137">`public class BankAccount` definiert die Klasse oder den Typ, die/den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="bed78-137">`public class BankAccount` defines the class, or type, you are creating.</span></span> <span data-ttu-id="bed78-138">Sämtliche Inhalte zwischen `{` und `}`, die der Klassendeklaration folgen, definieren das Verhalten der Klasse.</span><span class="sxs-lookup"><span data-stu-id="bed78-138">Everything inside the `{` and `}` that follows the class declaration defines the behavior of the class.</span></span> <span data-ttu-id="bed78-139">Die `BankAccount`-Klasse verfügt über fünf ***Member***.</span><span class="sxs-lookup"><span data-stu-id="bed78-139">There are five ***members*** of the `BankAccount` class.</span></span> <span data-ttu-id="bed78-140">Die ersten drei sind ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="bed78-140">The first three are ***properties***.</span></span> <span data-ttu-id="bed78-141">Eigenschaften sind Datenelemente und können Code aufweisen, der eine Überprüfung oder andere Regeln erzwingt.</span><span class="sxs-lookup"><span data-stu-id="bed78-141">Properties are data elements and can have code that enforces validation or other rules.</span></span> <span data-ttu-id="bed78-142">Die letzten beiden sind ***Methoden***.</span><span class="sxs-lookup"><span data-stu-id="bed78-142">The last two are ***methods***.</span></span> <span data-ttu-id="bed78-143">Methoden sind Codeblöcke, die eine einzelne Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="bed78-143">Methods are blocks of code that perform a single function.</span></span> <span data-ttu-id="bed78-144">Das Lesen der Namen der einzelnen Member sollte Ihnen oder anderen Entwicklern genug Informationen liefern, um zu verstehen, welche Aufgabe die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="bed78-144">Reading the names of each of the members should provide enough information for you or another developer to understand what the class does.</span></span>

## <a name="open-a-new-account"></a><span data-ttu-id="bed78-145">Eröffnen eines neuen Kontos</span><span class="sxs-lookup"><span data-stu-id="bed78-145">Open a new account</span></span>

<span data-ttu-id="bed78-146">Die erste zu implementierende Funktion ist das Eröffnen eines Bankkontos.</span><span class="sxs-lookup"><span data-stu-id="bed78-146">The first feature to implement is to open a bank account.</span></span> <span data-ttu-id="bed78-147">Wenn ein Kunde ein Konto eröffnet, muss er einen anfänglichen Kontostand bereitstellen und Informationen über den/die Besitzer dieses Kontos angeben.</span><span class="sxs-lookup"><span data-stu-id="bed78-147">When a customer opens an account, they must supply an initial balance, and information about the owner or owners of that account.</span></span> 

<span data-ttu-id="bed78-148">Das Erstellen eines neuen Objekts des `BankAccount`-Typs bedeutet Definieren eines ***Konstruktors***, der diese Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="bed78-148">Creating a new object of the `BankAccount` type means defining a ***constructor*** that assigns those values.</span></span> <span data-ttu-id="bed78-149">Ein ***Konstruktor*** ist ein Member, der den gleichen Namen wie die Klasse hat.</span><span class="sxs-lookup"><span data-stu-id="bed78-149">A ***constructor*** is a member that has the same name as the class.</span></span> <span data-ttu-id="bed78-150">Er wird verwendet, um Objekte dieses Klassentyps zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-150">It is used to initialize objects of that class type.</span></span> <span data-ttu-id="bed78-151">Fügen Sie dem `BankAccount`-Typ folgenden Konstruktor hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-151">Add the following constructor to the `BankAccount` type:</span></span>

```csharp
public BankAccount(string name, decimal initialBalance)
{
    this.Owner = name;
    this.Balance = initialBalance;
}
```

<span data-ttu-id="bed78-152">Konstruktoren werden bei der Erstellung eines Objekts mit [`new`](../../language-reference/keywords/new.md) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bed78-152">Constructors are called when you create an object using [`new`](../../language-reference/keywords/new.md).</span></span> <span data-ttu-id="bed78-153">Ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` in ***program.cs*** mit der folgenden Zeile (ersetzen Sie `<name>` durch Ihren Namen):</span><span class="sxs-lookup"><span data-stu-id="bed78-153">Replace the line `Console.WriteLine("Hello World!");` in ***program.cs*** with the following line (replace `<name>` with your name):</span></span>

```csharp
var account = new BankAccount("<name>", 1000);
Console.WriteLine($"Account {account.Number} was created for {account.Owner} with {account.Balance} initial balance.");
```

<span data-ttu-id="bed78-154">Geben Sie `dotnet run` ein, und beobachten Sie, was passiert.</span><span class="sxs-lookup"><span data-stu-id="bed78-154">Type `dotnet run` to see what happens.</span></span>  

<span data-ttu-id="bed78-155">Haben Sie bemerkt, dass die Kontonummer leer ist?</span><span class="sxs-lookup"><span data-stu-id="bed78-155">Did you notice that the account number is blank?</span></span> <span data-ttu-id="bed78-156">Es ist höchste Zeit, dies zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bed78-156">It's time to fix that.</span></span> <span data-ttu-id="bed78-157">Die Kontonummer sollten zugewiesen werden, wenn das Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bed78-157">The account number should be assigned when the object is constructed.</span></span> <span data-ttu-id="bed78-158">Jedoch sollte nicht der Aufrufende für das Erstellen verantwortlich sein.</span><span class="sxs-lookup"><span data-stu-id="bed78-158">But it shouldn't be the responsibility of the caller to create it.</span></span> <span data-ttu-id="bed78-159">Der `BankAccount`-Klassencode sollte wissen, wie neue Kontonummern zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="bed78-159">The `BankAccount` class code should know how to assign new account numbers.</span></span>  <span data-ttu-id="bed78-160">Eine einfache Möglichkeit hierzu ist, mit einer 10-stelligen Zahl zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="bed78-160">A simple way to do this is to start with a 10-digit number.</span></span> <span data-ttu-id="bed78-161">Lassen Sie sie bei jeder Erstellung eines neuen Kontos erhöhen.</span><span class="sxs-lookup"><span data-stu-id="bed78-161">Increment it when each new account is created.</span></span> <span data-ttu-id="bed78-162">Speichern Sie schließlich die aktuelle Kontonummer, wenn ein Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bed78-162">Finally, store the current account number when an object is constructed.</span></span>

<span data-ttu-id="bed78-163">Fügen Sie der `BankAccount`-Klasse die folgende Memberdeklaration hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-163">Add the following member declaration to the `BankAccount` class:</span></span>

```csharp
private static int accountNumberSeed = 1234567890;
```

<span data-ttu-id="bed78-164">Dies ist ein Datenelement.</span><span class="sxs-lookup"><span data-stu-id="bed78-164">This is a data member.</span></span> <span data-ttu-id="bed78-165">Es ist `private`, d.h. der Zugriff darauf ist nur über Code in der `BankAccount`-Klasse möglich.</span><span class="sxs-lookup"><span data-stu-id="bed78-165">It's `private`, which means it can only be accessed by code inside the `BankAccount` class.</span></span> <span data-ttu-id="bed78-166">Dies ist eine Möglichkeit, die öffentlichen Verantwortlichkeiten (z.B. Besitz einer Kontonummer) von der privaten Implementierung (wie Kontonummern generiert werden) zu trennen. Es ist auch als `static` definiert, wird also von allen ``BankAccount``-Objekten gemeinsam genutzt.</span><span class="sxs-lookup"><span data-stu-id="bed78-166">It's a way of separating the public responsibilities (like having an account number) from the private implementation (how account numbers are generated.) It is also `static`, which means it is shared by all of the ``BankAccount`` objects.</span></span> <span data-ttu-id="bed78-167">Der Wert einer nicht statischen Variable ist für jede Instanz des ``BankAccount``-Objekts eindeutig.</span><span class="sxs-lookup"><span data-stu-id="bed78-167">The value of a non-static variable is unique to each instance of the ``BankAccount`` object.</span></span> <span data-ttu-id="bed78-168">Fügen Sie dem Konstruktor die folgenden zwei Zeilen hinzu, um die Kontonummer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="bed78-168">Add the following two lines to the constructor to assign the account number:</span></span>

```csharp
this.Number = accountNumberSeed.ToString();
accountNumberSeed++;
```

<span data-ttu-id="bed78-169">Geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bed78-169">Type `dotnet run` to see the results.</span></span>

## <a name="create-deposits-and-withdrawals"></a><span data-ttu-id="bed78-170">Erstellen von Einzahlungen und Abbuchungen</span><span class="sxs-lookup"><span data-stu-id="bed78-170">Create deposits and withdrawals</span></span>

<span data-ttu-id="bed78-171">Um ordnungsgemäß zu funktionieren, muss Ihre Bankkontoklasse Einzahlungen und Abbuchungen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-171">Your bank account class needs to accept deposits and withdrawals to work correctly.</span></span> <span data-ttu-id="bed78-172">Einzahlungen und Abbuchungen implementieren Sie, indem Sie eine Erfassung jeder Transaktion für das Konto erstellen.</span><span class="sxs-lookup"><span data-stu-id="bed78-172">Let's implement deposits and withdrawals by creating a journal of every transaction for the account.</span></span> <span data-ttu-id="bed78-173">Dies ist vorteilhafter, als den Kontostand bei jeder Transaktion einfachen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-173">That has a few advantages over simply updating the balance on each transaction.</span></span> <span data-ttu-id="bed78-174">Der Verlauf kann zum Überwachen aller Transaktionen und Verwalten täglicher Kontostände verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bed78-174">The history can be used to audit all transactions and manage daily balances.</span></span> <span data-ttu-id="bed78-175">Indem der Kontostand ggf. aus dem Verlauf aller Transaktionen berechnet wird, werden etwaige Korrekturen von Fehlern in einer einzelnen Transaktion bei der nächsten Berechnung im Kontostand ordnungsgemäß widergespiegelt.</span><span class="sxs-lookup"><span data-stu-id="bed78-175">By computing the balance from the history of all transactions when needed, any errors in a single transaction that are fixed will be correctly reflected in the balance on the next computation.</span></span>

<span data-ttu-id="bed78-176">Zunächst erstellen wir einen neuen Typ, um eine Transaktion darzustellen.</span><span class="sxs-lookup"><span data-stu-id="bed78-176">Let's start by creating a new type to represent a transaction.</span></span> <span data-ttu-id="bed78-177">Dies ist ein einfacher Typ, der keine Verantwortlichkeiten hat.</span><span class="sxs-lookup"><span data-stu-id="bed78-177">This is a simple type that doesn't have any responsibilities.</span></span> <span data-ttu-id="bed78-178">Er benötigt einige Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="bed78-178">It needs a few properties.</span></span> <span data-ttu-id="bed78-179">Erstellen Sie eine neue Datei mit dem Namen ***Transaction.cs***.</span><span class="sxs-lookup"><span data-stu-id="bed78-179">Create a new file named ***Transaction.cs***.</span></span> <span data-ttu-id="bed78-180">Fügen Sie ihr folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-180">Add the following code to it:</span></span>

[!code-csharp[Transaction](../../../../samples/csharp/classes-quickstart/Transaction.cs "Transaction declaration")]

<span data-ttu-id="bed78-181">Nun fügen wir eine <xref:System.Collections.Generic.List%601> von `Transaction`-Objekten der `BankAccount`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="bed78-181">Now, let's add a <xref:System.Collections.Generic.List%601> of `Transaction` objects to the `BankAccount` class.</span></span> <span data-ttu-id="bed78-182">Fügen Sie die folgende Deklaration hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-182">Add the following declaration:</span></span>

[!code-csharp[TransactionDecl](../../../../samples/csharp/classes-quickstart/BankAccount.cs#TransactionDeclaration "Transaction declaration")]

<span data-ttu-id="bed78-183">Die <xref:System.Collections.Generic.List%601>-Klasse erfordert, dass Sie einen anderen Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-183">The <xref:System.Collections.Generic.List%601> class requires you to import a different namespace.</span></span> <span data-ttu-id="bed78-184">Fügen Sie am Anfang von **BankAccount.cs** Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-184">Add the following at the beginning of **BankAccount.cs**:</span></span>

```csharp
using System.Collections.Generic;
```

<span data-ttu-id="bed78-185">Jetzt ändern wir die Art, in der `Balance` gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="bed78-185">Now, let's change how the `Balance` is reported.</span></span>  <span data-ttu-id="bed78-186">Er kann durch Summierung der Werte aller Transaktionen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="bed78-186">It can be found by summing the values of all transactions.</span></span> <span data-ttu-id="bed78-187">Ändern Sie die Deklaration von `Balance` in der `BankAccount`-Klasse folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="bed78-187">Modify the declaration of `Balance` in the `BankAccount` class to the following:</span></span>

[!code-csharp[BalanceComputation](../../../../samples/csharp/classes-quickstart/BankAccount.cs#BalanceComputation "Computing the balance")]

<span data-ttu-id="bed78-188">Dieses Beispiel zeigt einen wichtigen Aspekt der ***Eigenschaften***.</span><span class="sxs-lookup"><span data-stu-id="bed78-188">This example shows an important aspect of ***properties***.</span></span> <span data-ttu-id="bed78-189">Jetzt berechnen Sie den Kontostand, wenn ein anderer Programmierer den Wert anfordert.</span><span class="sxs-lookup"><span data-stu-id="bed78-189">You're now computing the balance when another programmer asks for the value.</span></span> <span data-ttu-id="bed78-190">Die Berechnung zählt alle Transaktionen auf und gibt die Summe als aktuellen Kontostand zurück.</span><span class="sxs-lookup"><span data-stu-id="bed78-190">Your computation enumerates all transactions, and provides the sum as the current balance.</span></span>

<span data-ttu-id="bed78-191">Implementieren Sie nun die `MakeDeposit`- und `MakeWithdrawal`-Methode.</span><span class="sxs-lookup"><span data-stu-id="bed78-191">Next, implement the `MakeDeposit` and `MakeWithdrawal` methods.</span></span> <span data-ttu-id="bed78-192">Diese Methoden erzwingen die letzten beiden Regeln: Der anfängliche Kontostand muss positiv sein, und eine Abbuchung darf nicht in einem negativen Kontostand resultieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-192">These methods will enforce the final two rules: that the initial balance must be positive, and that any withdrawal must not create a negative balance.</span></span> 

<span data-ttu-id="bed78-193">Dies führt das Konzept der ***Ausnahmen*** ein.</span><span class="sxs-lookup"><span data-stu-id="bed78-193">This introduces the concept of ***exceptions***.</span></span> <span data-ttu-id="bed78-194">Standardmäßig wird eine Ausnahme ausgelöst, um anzuzeigen, dass eine Methode ihre Aufgabe nicht erfolgreich ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="bed78-194">The standard way of indicating that a method cannot complete its work successfully is to throw an exception.</span></span> <span data-ttu-id="bed78-195">Der Typ der Ausnahme und die zugeordnete Nachricht beschreiben den Fehler.</span><span class="sxs-lookup"><span data-stu-id="bed78-195">The type of exception and the message associated with it describe the error.</span></span> <span data-ttu-id="bed78-196">Hier löst die `MakeDeposit`-Methode eine Ausnahme aus, wenn der Einzahlungsbetrag negativ ist.</span><span class="sxs-lookup"><span data-stu-id="bed78-196">Here, the `MakeDeposit` method throws an exception if the amount of the deposit is negative.</span></span> <span data-ttu-id="bed78-197">Die `MakeWithdrawal`-Methode löst eine Ausnahme aus, wenn der Abbuchungsbetrag negativ ist, oder wenn aus der Abbuchung ein negativer Kontostand resultiert:</span><span class="sxs-lookup"><span data-stu-id="bed78-197">The `MakeWithdrawal` method throws an exception if the withdrawal amount is negative, or if applying the withdrawal results in a negative balance:</span></span>

[!code-csharp[DepositAndWithdrawal](../../../../samples/csharp/classes-quickstart/BankAccount.cs#DepositAndWithdrawal "Make deposits and withdrawals")]

<span data-ttu-id="bed78-198">Die [`throw`](../../language-reference/keywords/throw.md)-Anweisung **löst** eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="bed78-198">The [`throw`](../../language-reference/keywords/throw.md) statement **throws** an exception.</span></span> <span data-ttu-id="bed78-199">Die Ausführung des aktuellen Block wird beendet, und die Steuerung wird an den ersten übereinstimmenden `catch`-Block übertragen, der in der Aufrufliste gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="bed78-199">Execution of the current block ends, and control transfers to the first matching `catch` block found in the call stack.</span></span> <span data-ttu-id="bed78-200">Sie fügen einen `catch`-Block hinzu, um diesen Code etwas später zu testen.</span><span class="sxs-lookup"><span data-stu-id="bed78-200">You'll add a `catch` block to test this code a little later on.</span></span>

<span data-ttu-id="bed78-201">Der Konstruktor sollte so geändert werden, dass er eine anfängliche Transaktion hinzufügt, anstatt den Kontostand direkt zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="bed78-201">The constructor should get one change so that it adds an initial transaction, rather than updating the balance directly.</span></span> <span data-ttu-id="bed78-202">Da Sie die `MakeDeposit`-Methode bereits geschrieben haben, rufen Sie sie aus dem Konstruktor auf.</span><span class="sxs-lookup"><span data-stu-id="bed78-202">Since you already wrote the `MakeDeposit` method, call it from your constructor.</span></span> <span data-ttu-id="bed78-203">Der fertige Konstruktor sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bed78-203">The finished constructor should look like this:</span></span>

[!code-csharp[Constructor](../../../../samples/csharp/classes-quickstart/BankAccount.cs#Constructor "The final version of the constructor")]

<span data-ttu-id="bed78-204"><xref:System.DateTime.Now?displayProperty=nameWithType> ist eine Eigenschaft, die das aktuelle Datum und die Uhrzeit zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bed78-204"><xref:System.DateTime.Now?displayProperty=nameWithType> is a property that returns the current date and time.</span></span> <span data-ttu-id="bed78-205">Testen Sie dies durch Hinzufügen von ein paar Einzahlungen und Abbuchungen in Ihrer `Main`-Methode:</span><span class="sxs-lookup"><span data-stu-id="bed78-205">Test this by adding a few deposits and withdrawals in your `Main` method:</span></span>

```csharp
account.MakeWithdrawal(500, DateTime.Now, "Rent payment");
Console.WriteLine(account.Balance);
account.MakeDeposit(100, DateTime.Now, "friend paid me back");
Console.WriteLine(account.Balance);
```

<span data-ttu-id="bed78-206">Testen Sie anschließend, ob Sie Fehlerbedingungen abfangen, indem Sie versuchen, ein Konto mit einem negativen Kontostand zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bed78-206">Next, test that you are catching error conditions by trying to create an account with a negative balance:</span></span>

```csharp
// Test that the initial balances must be positive:
try
{
    var invalidAccount = new BankAccount("invalid", -55);
}
catch (ArgumentOutOfRangeException e)
{
    Console.WriteLine("Exception caught creating account with negative balance");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="bed78-207">Sie verwenden die [Anweisungen `try` und `catch`](../../language-reference/keywords/try-catch.md), um einen Codeblock zu markieren, der Ausnahmen auslösen kann, und um die erwarteten Fehler abzufangen.</span><span class="sxs-lookup"><span data-stu-id="bed78-207">You use the [`try` and `catch` statements](../../language-reference/keywords/try-catch.md) to mark a block of code that may throw exceptions and to catch those errors that you expect.</span></span> <span data-ttu-id="bed78-208">Mit dem gleichen Verfahren können Sie den Code testen, der bei einem negativen Kontostand eine Ausnahme auslöst:</span><span class="sxs-lookup"><span data-stu-id="bed78-208">You can use the same technique to test the code that throws an exception for a negative balance:</span></span>

```csharp
// Test for a negative balance
try
{
    account.MakeWithdrawal(750, DateTime.Now, "Attempt to overdraw");
}
catch (InvalidOperationException e)
{
    Console.WriteLine("Exception caught trying to overdraw");
    Console.WriteLine(e.ToString());
}
```

<span data-ttu-id="bed78-209">Speichern Sie die Datei, und geben Sie `dotnet run` zum Testen ein.</span><span class="sxs-lookup"><span data-stu-id="bed78-209">Save the file and type `dotnet run` to try it.</span></span>

## <a name="challenge---log-all-transactions"></a><span data-ttu-id="bed78-210">Herausforderung – Protokollieren aller Transaktionen</span><span class="sxs-lookup"><span data-stu-id="bed78-210">Challenge - log all transactions</span></span>

<span data-ttu-id="bed78-211">Um dieses Tutorial abzuschließen, können Sie die `GetAccountHistory`-Methode schreiben, die eine Zeichenfolge (`string`) für den Transaktionsverlauf erstellt.</span><span class="sxs-lookup"><span data-stu-id="bed78-211">To finish this tutorial, you can write the `GetAccountHistory` method that creates a `string` for the transaction history.</span></span> <span data-ttu-id="bed78-212">Fügen Sie diese Methode dem `BankAccount`-Typ hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-212">Add this method to the `BankAccount` type:</span></span>

[!code-csharp[History](../../../../samples/csharp/classes-quickstart/BankAccount.cs#History "Display transaction history")]

<span data-ttu-id="bed78-213">Hier wird die <xref:System.Text.StringBuilder>-Klasse zum Formatieren einer Zeichenfolge verwendet, die eine Zeile für jede Transaktion enthält.</span><span class="sxs-lookup"><span data-stu-id="bed78-213">This uses the <xref:System.Text.StringBuilder> class to format a string that contains one line for each transaction.</span></span> <span data-ttu-id="bed78-214">Sie haben den Zeichenfolgen-Formatierungscode in diesen Tutorials bereits gesehen.</span><span class="sxs-lookup"><span data-stu-id="bed78-214">You've seen the string formatting code earlier in these tutorials.</span></span> <span data-ttu-id="bed78-215">`\t` ist ein neues Zeichen.</span><span class="sxs-lookup"><span data-stu-id="bed78-215">One new character is `\t`.</span></span> <span data-ttu-id="bed78-216">Damit wird ein Tabulator zum Formatieren der Ausgabe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bed78-216">That inserts a tab to format the output.</span></span>

<span data-ttu-id="bed78-217">Fügen Sie diese Zeile **Program.cs** zum Testen hinzu:</span><span class="sxs-lookup"><span data-stu-id="bed78-217">Add this line to test it in **Program.cs**:</span></span>

```csharp
Console.WriteLine(account.GetAccountHistory());
```

<span data-ttu-id="bed78-218">Geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bed78-218">Type `dotnet run` to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bed78-219">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bed78-219">Next Steps</span></span>

<span data-ttu-id="bed78-220">Wenn Sie nicht weiterkommen, sehen Sie sich die Quelle für dieses Tutorial [in unserem GitHub-Repository](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/) an.</span><span class="sxs-lookup"><span data-stu-id="bed78-220">If you got stuck, you can see the source for this tutorial [in our GitHub repo](https://github.com/dotnet/samples/tree/master/csharp/classes-quickstart/)</span></span>

<span data-ttu-id="bed78-221">Herzlichen Glückwunsch! Sie haben unsere Tutorials zur Einführung in C# vollständig abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bed78-221">Congratulations, you've finished all our introduction to C# tutorials.</span></span> <span data-ttu-id="bed78-222">Wenn Sie mehr lernen möchten, sehen Sie sich weitere [Tutorials](../index.md) an.</span><span class="sxs-lookup"><span data-stu-id="bed78-222">If you're eager to learn more, try more of our [tutorials](../index.md)</span></span>