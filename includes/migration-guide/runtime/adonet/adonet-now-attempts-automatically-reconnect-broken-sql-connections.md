### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="ad7e3-101">ADO.NET versucht nun, unterbrochene SQL-Verbindungen automatisch wiederherzustellen</span><span class="sxs-lookup"><span data-stu-id="ad7e3-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ad7e3-102">Details</span><span class="sxs-lookup"><span data-stu-id="ad7e3-102">Details</span></span>|<span data-ttu-id="ad7e3-103">Ab .NET Framework 4.5.1 versucht .NET Framework, unterbrochene SQL-Verbindungen automatisch wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="ad7e3-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="ad7e3-104">Obwohl dies in der Regel dazu führt, dass Apps zuverlässiger werden, gibt es Grenzfälle, in denen eine App wissen muss, dass die Verbindung getrennt wurde, sodass sie bei der Wiederherstellung der Verbindung bestimmte Aktionen ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="ad7e3-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>|
|<span data-ttu-id="ad7e3-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ad7e3-105">Suggestion</span></span>|<span data-ttu-id="ad7e3-106">Wenn dieses Feature aus Kompatibilitätsgründen nicht erwünscht ist, kann es durch Festlegen der <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=name>-Eigenschaft einer Verbindungszeichenfolge (oder <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=name>) auf 0 (null) deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ad7e3-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=name> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=name>) to 0.</span></span>|
|<span data-ttu-id="ad7e3-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="ad7e3-107">Scope</span></span>|<span data-ttu-id="ad7e3-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ad7e3-108">Edge</span></span>|
|<span data-ttu-id="ad7e3-109">Version</span><span class="sxs-lookup"><span data-stu-id="ad7e3-109">Version</span></span>|<span data-ttu-id="ad7e3-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="ad7e3-110">4.5.1</span></span>|
|<span data-ttu-id="ad7e3-111">Typ</span><span class="sxs-lookup"><span data-stu-id="ad7e3-111">Type</span></span>|<span data-ttu-id="ad7e3-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ad7e3-112">Runtime</span></span>|
|<span data-ttu-id="ad7e3-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ad7e3-113">Affected APIs</span></span>|<ul><li><xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)?displayProperty=nameWithType></li></ul>|
