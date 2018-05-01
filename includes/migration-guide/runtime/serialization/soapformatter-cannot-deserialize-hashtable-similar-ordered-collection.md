### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="fc1bb-101">Hashtable und ähnlich sortierte Auflistungsobjekte können von SoapFormatter nicht deserialisiert werden</span><span class="sxs-lookup"><span data-stu-id="fc1bb-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fc1bb-102">Details</span><span class="sxs-lookup"><span data-stu-id="fc1bb-102">Details</span></span>|<span data-ttu-id="fc1bb-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> garantiert nicht dafür, dass unter einer .NET Framework-Version serialisierte Objekte erfolgreich unter einer anderen Version deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="fc1bb-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="fc1bb-104">Insbesondere einige sortierte Auflistungen (z.B. <xref:System.Collections.Hashtable?displayProperty=name>) haben Member zwischen 4.0 und 4.5 hinzugefügt, sodass Objekte dieser Typen nicht mit .NET 4.0 deserialisiert werden können, wenn sie mit .NET 4.5 serialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fc1bb-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=name>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET 4.0 if they were serialized with .NET 4.5.</span></span> <span data-ttu-id="fc1bb-105">Beachten Sie, dass kein Problem auftritt, wenn die serialisierten Daten mit derselben Version von .NET Framework sowohl serialisiert als auch deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc1bb-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>|
|<span data-ttu-id="fc1bb-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fc1bb-106">Suggestion</span></span>|<span data-ttu-id="fc1bb-107">Die <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name>-Serialisierung sollte durch die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name>-Serialisierung oder durch <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> ersetzt werden, um .NET Framework-Änderungen verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="fc1bb-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> to be resilient to .NET Framework changes.</span></span>|
|<span data-ttu-id="fc1bb-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="fc1bb-108">Scope</span></span>|<span data-ttu-id="fc1bb-109">Gering</span><span class="sxs-lookup"><span data-stu-id="fc1bb-109">Minor</span></span>|
|<span data-ttu-id="fc1bb-110">Version</span><span class="sxs-lookup"><span data-stu-id="fc1bb-110">Version</span></span>|<span data-ttu-id="fc1bb-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fc1bb-111">4.5</span></span>|
|<span data-ttu-id="fc1bb-112">Typ</span><span class="sxs-lookup"><span data-stu-id="fc1bb-112">Type</span></span>|<span data-ttu-id="fc1bb-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fc1bb-113">Runtime</span></span>|
|<span data-ttu-id="fc1bb-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fc1bb-114">Affected APIs</span></span>|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
