---
title: Contadores de desempenho no ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: e60df2b576980ecd1ff92af78cef36f025b71417
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903788"
---
# <a name="performance-counters-in-adonet"></a>Contadores de desempenho no ADO.NET
O ADO.NET 2.0 introduziu suporte expandido para contadores de desempenho que inclui suporte para ambos <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>. O <xref:System.Data.SqlClient> contadores de desempenho disponíveis nas versões anteriores do ADO.NET foram preteridos e substituídos por novos contadores de desempenho discutidos neste tópico. Você pode usar contadores de desempenho do ADO.NET para monitorar o status do seu aplicativo e os recursos de conexão que ele usa. Contadores de desempenho podem ser monitorados usando o Monitor de desempenho do Windows ou podem ser acessados por meio de programação usando o <xref:System.Diagnostics.PerformanceCounter> classe o <xref:System.Diagnostics> namespace.  
  
## <a name="available-performance-counters"></a>Contadores de desempenho disponíveis  
 Atualmente, há 14 diferentes contadores de desempenho disponíveis para <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient> conforme descrito na tabela a seguir. Observe que os nomes dos contadores individuais não são localizados em versões regionais do Microsoft .NET Framework.  
  
|Contador de desempenho|Descrição|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|O número de conexões por segundo que estão sendo feitas em um servidor de banco de dados.|  
|`HardDisconnectsPerSecond`|O número de desconexões por segundo que estão sendo feitas em um servidor de banco de dados.|  
|`NumberOfActiveConnectionPoolGroups`|O número de grupos de pools de conexão exclusiva que estão ativos. Esse contador é controlado pelo número de cadeias de caracteres de conexão exclusiva que são encontradas no AppDomain.|  
|`NumberOfActiveConnectionPools`|O número total de pools de conexão.|  
|`NumberOfActiveConnections`|O número de conexões ativas que estão atualmente em uso. **Observação:**  Esse contador de desempenho não está habilitado por padrão. Para habilitar esse contador de desempenho, consulte [ativando desativado por padrão contadores](#ActivatingOffByDefault).|  
|`NumberOfFreeConnections`|O número de conexões disponíveis para uso nos pools de conexão. **Observação:**  Esse contador de desempenho não está habilitado por padrão. Para habilitar esse contador de desempenho, consulte [ativando desativado por padrão contadores](#ActivatingOffByDefault).|  
|`NumberOfInactiveConnectionPoolGroups`|O número de grupos de pools de conexão exclusiva que são marcados para remoção. Esse contador é controlado pelo número de cadeias de caracteres de conexão exclusiva que são encontradas no AppDomain.|  
|`NumberOfInactiveConnectionPools`|O número de pools de conexão inativa que não tiveram nenhuma atividade recente e estão aguardando para ser descartado.|  
|`NumberOfNonPooledConnections`|O número de conexões ativas e não em pool.|  
|`NumberOfPooledConnections`|O número de conexões ativas que estão sendo gerenciadas pela infra-estrutura de pooling de conexão.|  
|`NumberOfReclaimedConnections`|O número de conexões que foram recuperados por meio de coleta de lixo em que `Close` ou `Dispose` não foi chamado pelo aplicativo. Fechando não explicitamente ou descartar conexões reduz o desempenho.|  
|`NumberOfStasisConnections`|O número de conexões aguardando a conclusão de uma ação e que, portanto, não está disponível para uso pelo seu aplicativo no momento.|  
|`SoftConnectsPerSecond`|O número de conexões ativas sendo obtido do pool de conexão. **Observação:**  Esse contador de desempenho não está habilitado por padrão. Para habilitar esse contador de desempenho, consulte [ativando desativado por padrão contadores](#ActivatingOffByDefault).|  
|`SoftDisconnectsPerSecond`|O número de conexões ativas que estão sendo retornados ao pool de conexão. **Observação:**  Esse contador de desempenho não está habilitado por padrão. Para habilitar esse contador de desempenho, consulte [ativando desativado por padrão contadores](#ActivatingOffByDefault).|  
  
### <a name="connection-pool-groups-and-connection-pools"></a>Grupos de pools de Conexão e Pools de Conexão  
 Ao usar a autenticação do Windows (segurança integrada), você deve monitorar tanto a `NumberOfActiveConnectionPoolGroups` e `NumberOfActiveConnectionPools` contadores de desempenho. O motivo é que esse mapa de grupos do pool de conexão em cadeias de caracteres de conexão exclusivo. Quando a segurança integrada é usada, pools de conexão do mapa em cadeias de caracteres de conexão e Além disso, criar grupos separados para identidades individuais do Windows. Por exemplo, se Fred e Julie, cada um dentro do mesmo AppDomain, ambos usam a cadeia de caracteres de conexão `"Data Source=MySqlServer;Integrated Security=true"`, um grupo de pool de conexão é criado para a cadeia de caracteres de conexão e dois pools adicionais são criados, um para Fred e outro para Julie. Se João e Martha usam uma cadeia de caracteres de conexão com um logon do SQL Server idêntico, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, em seguida, apenas um único pool é criado para o **lowPrivUser** identidade.  
  
<a name="ActivatingOffByDefault"></a>   
### <a name="activating-off-by-default-counters"></a>Ativar os contadores de desativado por padrão  
 Os contadores de desempenho `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond`, e `SoftConnectsPerSecond` são desativados por padrão. Adicione as seguintes informações ao arquivo de configuração do aplicativo para habilitá-los:  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a>Recuperando valores de contador de desempenho  
 O aplicativo de console a seguir mostra como recuperar valores de contador de desempenho em seu aplicativo. Conexões devem ser aberto e ativo para obter informações a serem retornadas para todos os contadores de desempenho do ADO.NET.  
  
> [!NOTE]
>  Este exemplo usa a amostra **AdventureWorks** banco de dados incluído com o SQL Server. As cadeias de caracteres de conexão fornecidas no código de exemplo pressupõem que o banco de dados está instalado e disponível no computador local com um nome de instância de SqlExpress, e que você tenha criado os logons do SQL Server que correspondam àquelas fornecidas nas cadeias de conexão. Talvez você precise habilitar os logons do SQL Server se o servidor é configurado usando as configurações de segurança padrão que permitem que somente a autenticação do Windows. Modificar as cadeias de caracteres de conexão conforme necessário para se adequar ao seu ambiente.  
  
### <a name="example"></a>Exemplo  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System.Data.SqlClient  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Class Program  
  
    Private PerfCounters(9) As PerformanceCounter  
    Private connection As SqlConnection = New SqlConnection  
  
    Public Shared Sub Main()  
        Dim prog As Program = New Program  
        ' Open a connection and create the performance counters.   
        prog.connection.ConnectionString = _  
           GetIntegratedSecurityConnectionString()  
        prog.SetUpPerformanceCounters()  
        Console.WriteLine("Available Performance Counters:")  
  
        ' Create the connections and display the results.  
        prog.CreateConnections()  
        Console.WriteLine("Press Enter to finish.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub CreateConnections()  
        ' List the Performance counters.  
        WritePerformanceCounters()  
  
        ' Create 4 connections and display counter information.  
        Dim connection1 As SqlConnection = New SqlConnection( _  
           GetIntegratedSecurityConnectionString)  
        connection1.Open()  
        Console.WriteLine("Opened the 1st Connection:")  
        WritePerformanceCounters()  
  
        Dim connection2 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionStringDifferent)  
        connection2.Open()  
        Console.WriteLine("Opened the 2nd Connection:")  
        WritePerformanceCounters()  
  
        Console.WriteLine("Opened the 3rd Connection:")  
        Dim connection3 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection3.Open()  
        WritePerformanceCounters()  
  
        Dim connection4 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection4.Open()  
        Console.WriteLine("Opened the 4th Connection:")  
        WritePerformanceCounters()  
  
        connection1.Close()  
        Console.WriteLine("Closed the 1st Connection:")  
        WritePerformanceCounters()  
  
        connection2.Close()  
        Console.WriteLine("Closed the 2nd Connection:")  
        WritePerformanceCounters()  
  
        connection3.Close()  
        Console.WriteLine("Closed the 3rd Connection:")  
        WritePerformanceCounters()  
  
        connection4.Close()  
        Console.WriteLine("Closed the 4th Connection:")  
        WritePerformanceCounters()  
    End Sub  
  
    Private Enum ADO_Net_Performance_Counters  
        NumberOfActiveConnectionPools  
        NumberOfReclaimedConnections  
        HardConnectsPerSecond  
        HardDisconnectsPerSecond  
        NumberOfActiveConnectionPoolGroups  
        NumberOfInactiveConnectionPoolGroups  
        NumberOfInactiveConnectionPools  
        NumberOfNonPooledConnections  
        NumberOfPooledConnections  
        NumberOfStasisConnections  
        ' The following performance counters are more expensive to track.  
        ' Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        '     SoftConnectsPerSecond  
        '     SoftDisconnectsPerSecond  
        '     NumberOfActiveConnections  
        '     NumberOfFreeConnections  
    End Enum  
  
    Private Sub SetUpPerformanceCounters()  
        connection.Close()  
        Me.PerfCounters(9) = New PerformanceCounter()  
  
        Dim instanceName As String = GetInstanceName()  
        Dim apc As Type = GetType(ADO_Net_Performance_Counters)  
        Dim i As Integer = 0  
        Dim s As String = ""  
        For Each s In [Enum].GetNames(apc)  
            Me.PerfCounters(i) = New PerformanceCounter()  
            Me.PerfCounters(i).CategoryName = ".NET Data Provider for SqlServer"  
            Me.PerfCounters(i).CounterName = s  
            Me.PerfCounters(i).InstanceName = instanceName  
            i = (i + 1)  
        Next  
    End Sub  
  
    Private Declare Function GetCurrentProcessId Lib "kernel32.dll" () As Integer  
  
    Private Function GetInstanceName() As String  
        'This works for Winforms apps.   
        Dim instanceName As String = _  
           System.Reflection.Assembly.GetEntryAssembly.GetName.Name  
  
        ' Must replace special characters like (, ), #, /, \\   
        Dim instanceName2 As String = _  
           AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
           .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        'For ASP.NET applications your instanceName will be your CurrentDomain's   
        'FriendlyName. Replace the line above that sets the instanceName with this:   
        'instanceName = AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
        '    .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        Dim pid As String = GetCurrentProcessId.ToString  
        instanceName = (instanceName + ("[" & (pid & "]")))  
        Console.WriteLine("Instance Name: {0}", instanceName)  
        Console.WriteLine("---------------------------")  
        Return instanceName  
    End Function  
  
    Private Sub WritePerformanceCounters()  
        Console.WriteLine("---------------------------")  
        For Each p As PerformanceCounter In Me.PerfCounters  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue)  
        Next  
        Console.WriteLine("---------------------------")  
    End Sub  
  
    Private Shared Function GetIntegratedSecurityConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;Integrated Security=True;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionStringDifferent() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _  
          "User Id=LowPriv;Password=Data!05;")  
    End Function  
End Class  
```  

```csharp  
using System;  
using System.Data.SqlClient;  
using System.Diagnostics;  
using System.Runtime.InteropServices;  
  
class Program  
{  
    PerformanceCounter[] PerfCounters = new PerformanceCounter[10];  
    SqlConnection connection = new SqlConnection();  
  
    static void Main()  
    {  
        Program prog = new Program();  
        // Open a connection and create the performance counters.  
        prog.connection.ConnectionString =  
           GetIntegratedSecurityConnectionString();  
        prog.SetUpPerformanceCounters();  
        Console.WriteLine("Available Performance Counters:");  
  
        // Create the connections and display the results.  
        prog.CreateConnections();  
        Console.WriteLine("Press Enter to finish.");  
        Console.ReadLine();  
    }  
  
    private void CreateConnections()  
    {  
        // List the Performance counters.  
        WritePerformanceCounters();  
  
        // Create 4 connections and display counter information.  
        SqlConnection connection1 = new SqlConnection(  
              GetIntegratedSecurityConnectionString());  
        connection1.Open();  
        Console.WriteLine("Opened the 1st Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection2 = new SqlConnection(  
              GetSqlConnectionStringDifferent());  
        connection2.Open();  
        Console.WriteLine("Opened the 2nd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection3 = new SqlConnection(  
              GetSqlConnectionString());  
        connection3.Open();  
        Console.WriteLine("Opened the 3rd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection4 = new SqlConnection(  
              GetSqlConnectionString());  
        connection4.Open();  
        Console.WriteLine("Opened the 4th Connection:");  
        WritePerformanceCounters();  
  
        connection1.Close();  
        Console.WriteLine("Closed the 1st Connection:");  
        WritePerformanceCounters();  
  
        connection2.Close();  
        Console.WriteLine("Closed the 2nd Connection:");  
        WritePerformanceCounters();  
  
        connection3.Close();  
        Console.WriteLine("Closed the 3rd Connection:");  
        WritePerformanceCounters();  
  
        connection4.Close();  
        Console.WriteLine("Closed the 4th Connection:");  
        WritePerformanceCounters();  
    }  
  
    private enum ADO_Net_Performance_Counters  
    {  
        NumberOfActiveConnectionPools,  
        NumberOfReclaimedConnections,  
        HardConnectsPerSecond,  
        HardDisconnectsPerSecond,  
        NumberOfActiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPools,  
        NumberOfNonPooledConnections,  
        NumberOfPooledConnections,  
        NumberOfStasisConnections  
        // The following performance counters are more expensive to track.  
        // Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        //     SoftConnectsPerSecond  
        //     SoftDisconnectsPerSecond  
        //     NumberOfActiveConnections  
        //     NumberOfFreeConnections  
    }  
  
    private void SetUpPerformanceCounters()  
    {  
        connection.Close();  
        this.PerfCounters = new PerformanceCounter[10];  
        string instanceName = GetInstanceName();  
        Type apc = typeof(ADO_Net_Performance_Counters);  
        int i = 0;  
        foreach (string s in Enum.GetNames(apc))  
        {  
            this.PerfCounters[i] = new PerformanceCounter();  
            this.PerfCounters[i].CategoryName = ".NET Data Provider for SqlServer";  
            this.PerfCounters[i].CounterName = s;  
            this.PerfCounters[i].InstanceName = instanceName;  
            i++;  
        }  
    }  
  
    [DllImport("kernel32.dll", SetLastError = true)]  
    static extern int GetCurrentProcessId();  
  
    private string GetInstanceName()  
    {  
        //This works for Winforms apps.  
        string instanceName =  
            System.Reflection.Assembly.GetEntryAssembly().GetName().Name;  
  
        // Must replace special characters like (, ), #, /, \\  
        string instanceName2 =  
            AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(', '[')  
            .Replace(')', ']').Replace('#', '_').Replace('/', '_').Replace('\\', '_');  
  
        // For ASP.NET applications your instanceName will be your CurrentDomain's   
        // FriendlyName. Replace the line above that sets the instanceName with this:  
        // instanceName = AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(','[')  
        // .Replace(')',']').Replace('#','_').Replace('/','_').Replace('\\','_');  
  
        string pid = GetCurrentProcessId().ToString();  
        instanceName = instanceName + "[" + pid + "]";  
        Console.WriteLine("Instance Name: {0}", instanceName);  
        Console.WriteLine("---------------------------");  
        return instanceName;  
    }  
  
    private void WritePerformanceCounters()  
    {  
        Console.WriteLine("---------------------------");  
        foreach (PerformanceCounter p in this.PerfCounters)  
        {  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue());  
        }  
        Console.WriteLine("---------------------------");  
    }  
  
    private static string GetIntegratedSecurityConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;Integrated Security=True;" +  
          "Initial Catalog=AdventureWorks";  
    }  
    private static string GetSqlConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" +  
          "Initial Catalog=AdventureWorks";  
    }  
  
    private static string GetSqlConnectionStringDifferent()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +  
          "User Id=LowPriv;Password=Data!05;";  
    }  
}  
```  

## <a name="see-also"></a>Consulte também
- [Conectando a uma fonte de dados](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Conexão do Oracle, ODBC e OLE DB Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)
- [Contadores de desempenho para ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))
- [Criação de perfil do tempo de execução](../../../../docs/framework/debug-trace-profile/runtime-profiling.md)
- [Introdução ao monitoramento de limites de desempenho](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))
- [ADO.NET Overview](ado-net-overview.md) (Visão geral do ADO.NET)
