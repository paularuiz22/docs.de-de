---
title: Azure Logic Apps – serverlose apps
description: Mit Azure Logic Apps ermöglichen die Entwicklung automatisierter skalierbarer Workflows, die apps integrieren und Daten übergreifend in Clouddienste und lokalen Systemen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 019539f0da1d38259870907c38ed0eb6a62f1929
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369949"
---
# <a name="azure-logic-apps"></a><span data-ttu-id="45ee4-103">Azure-Logik-Apps</span><span class="sxs-lookup"><span data-stu-id="45ee4-103">Azure Logic Apps</span></span>

<span data-ttu-id="45ee4-104">[Mit Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) bietet eine serverlose-Engine zum Erstellen von automatisierten Workflows zum Integrieren von apps und Daten zwischen Cloud-Diensten und lokalen Systemen.</span><span class="sxs-lookup"><span data-stu-id="45ee4-104">[Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps) provides a serverless engine to build automated workflows to integrate apps and data between cloud services and on-premises systems.</span></span> <span data-ttu-id="45ee4-105">Erstellen Sie Workflows, die mit einem visuellen Designer.</span><span class="sxs-lookup"><span data-stu-id="45ee4-105">You build workflows using a visual designer.</span></span> <span data-ttu-id="45ee4-106">Sie können basierend auf Ereignisse oder Timer und Connectors nutzen integrationsanwendungen Workflows auslösen und erleichtern die Kommunikation von Business-to-Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="45ee4-106">You can trigger workflows based on events or timers and leverage connectors to integration applications and facilitate business-to-business (B2B) communication.</span></span> <span data-ttu-id="45ee4-107">Logik-Apps integriert sich nahtlos mit Azure Functions.</span><span class="sxs-lookup"><span data-stu-id="45ee4-107">Logic Apps integrates seamlessly with Azure Functions.</span></span>

![Azure Logic Apps-logo](./media/logic-apps-logo.png)

<span data-ttu-id="45ee4-109">Logik-Apps mit Cloud-Ressourcen (z. B. Warteschlangen und -Datenbanken) ist mehr als verbinden Sie einfach auf Ihre Cloud-Dienste (z. B. Funktionen) möglich.</span><span class="sxs-lookup"><span data-stu-id="45ee4-109">Logic Apps can do more than just connect your cloud services (like functions) with cloud resources (like queues and databases).</span></span> <span data-ttu-id="45ee4-110">Sie können auch auf lokale Workflows mit dem lokalen Gateway orchestrieren.</span><span class="sxs-lookup"><span data-stu-id="45ee4-110">You can also orchestrate on-premises workflows with the on-premises gateway.</span></span> <span data-ttu-id="45ee4-111">Die Logik-App können Sie beispielsweise eine lokale SQL gespeicherten Prozedur als Reaktion auf eine Cloud-basierten-Ereignis oder bedingte Logik in Ihrem Workflow auslösen.</span><span class="sxs-lookup"><span data-stu-id="45ee4-111">For example, you can use the Logic App to trigger an on-premises SQL stored procedure in response to a cloud-based event or conditional logic in your workflow.</span></span> <span data-ttu-id="45ee4-112">Erfahren Sie mehr über [eine Verbindung mit lokalen Datenquellen mit Azure On-Premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span><span class="sxs-lookup"><span data-stu-id="45ee4-112">Learn more about [Connecting to on-premises data sources with Azure On-premises Data Gateway](https://docs.microsoft.com/azure/analysis-services/analysis-services-gateway).</span></span>

![Logik-Apps-Architektur](./media/logic-apps-architecture.png)

<span data-ttu-id="45ee4-114">Wie Azure Functions beginnen Sie mit einem Trigger-Logik-App-Workflows ein.</span><span class="sxs-lookup"><span data-stu-id="45ee4-114">Like Azure Functions, you kick off Logic App workflows with a trigger.</span></span> <span data-ttu-id="45ee4-115">Es gibt viele Trigger für die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="45ee4-115">There are many triggers for you to choose from.</span></span> <span data-ttu-id="45ee4-116">Die folgende Erfassung zeigt einige der gängigeren werden von Hunderten, die verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="45ee4-116">The following capture shows just a few of the more popular ones out of hundreds that are available.</span></span>

![Logik-Apps-Trigger](./media/logic-app-triggers.png)

<span data-ttu-id="45ee4-118">Sobald die app ausgelöst wird, können Sie den visuellen Designer, um Schritte, Schleifen, Bedingungen und Aktionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45ee4-118">Once the app is triggered, you can use the visual designer to build out steps, loops, conditions, and actions.</span></span> <span data-ttu-id="45ee4-119">In einem vorherigen Schritt an erfassten Daten ist für die Verwendung in den nachfolgenden Schritten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="45ee4-119">Any data ingested in a previous step is available for you to use in subsequent steps.</span></span> <span data-ttu-id="45ee4-120">Der folgende Workflow lädt URLs aus einer CosmosDB-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="45ee4-120">The following workflow loads URLs from a CosmosDB database.</span></span> <span data-ttu-id="45ee4-121">Diejenigen mit einer Vielzahl gefundenen `t.co` sucht sie auf Twitter.</span><span class="sxs-lookup"><span data-stu-id="45ee4-121">It finds the ones with a host of `t.co` then searches for them on Twitter.</span></span> <span data-ttu-id="45ee4-122">Wenn entsprechende Tweets gefunden wird, aktualisiert sie die Dokumente mit der entsprechenden Tweets durch Aufrufen der Funktion.</span><span class="sxs-lookup"><span data-stu-id="45ee4-122">If it finds corresponding tweets, it updates the documents with the related tweets by calling a function.</span></span>

![Logik-App-workflow](./media/logic-app-workflow.png)

<span data-ttu-id="45ee4-124">Die Logik-Apps-Dashboard zeigt den Verlauf der ausgeführten Workflows und gibt an, ob Ausführen jeder abgeschlossenen erfolgreich oder nicht.</span><span class="sxs-lookup"><span data-stu-id="45ee4-124">The Logic Apps dashboard shows the history of running your workflows and whether each run completed successfully or not.</span></span> <span data-ttu-id="45ee4-125">In einer bestimmten Ausführung navigieren können und überprüfen Sie die Daten, die einzelnen Schritte zur Problembehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45ee4-125">You can navigate into any given run and inspect the data used by each step for troubleshooting.</span></span> <span data-ttu-id="45ee4-126">Logic Apps bietet auch vorhandene Vorlagen, die Sie bearbeiten können, und eignen sich hervorragend für komplexe Enterprise-Workflows.</span><span class="sxs-lookup"><span data-stu-id="45ee4-126">Logic Apps also provides existing templates you can edit and are well suited for complex enterprise workflows.</span></span>

<span data-ttu-id="45ee4-127">Weitere Informationen finden Sie unter [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span><span class="sxs-lookup"><span data-stu-id="45ee4-127">To learn more, see [Azure Logic Apps](https://docs.microsoft.com/azure/logic-apps).</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="45ee4-128">[Zurück](application-insights.md)
[Weiter](event-grid.md)</span><span class="sxs-lookup"><span data-stu-id="45ee4-128">[Previous](application-insights.md)
[Next](event-grid.md)</span></span>