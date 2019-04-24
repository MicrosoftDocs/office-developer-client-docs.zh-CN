---
title: InfoPath、RPC 编码和 Web 服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f8d7b944-a8fd-9c5f-8f66-0f1b628b7c6e
description: Web 服务可以向描述 Web 服务的 Web 服务描述语言 (WSDL) 协定中的 Web 方法公开两种绑定样式中的一种：Document 或 RPC。
ms.openlocfilehash: 0eacf013c9cdf74f18f3de1d4412ca4ca165a960
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303526"
---
# <a name="infopath-rpc-encoding-and-web-services"></a>InfoPath、RPC 编码和 Web 服务

Web 服务可以向描述 Web 服务的 Web 服务描述语言 (WSDL) 协定中的 Web 方法公开两种绑定样式中的一种：Document 或 RPC。此外，还可以将这两种绑定样式中的每一种分别指定为 literal 或 encoded。每种类型最常见的实施方法是：document/literal 和 RPC/encoded。但是，Microsoft InfoPath 只支持连接到使用 document/literal 样式的 Web 服务。
  
大多数 Web 服务开发工具都提供用于指定要创建的 Web 服务种类的开关。如果要开发将从 InfoPath 进行连接的 Web 服务，则应指定 document/literal 作为 Web 服务的样式和编码。
  
但是，如果您对要使用的 Web 服务没有控制权，并且必须连接到使用 RPC/encoded 样式的 Web 服务，则可以使用 .NET 代理服务连接到 RPC/encoded Web 服务。
  
## <a name="using-a-net-proxy-service-to-connect-to-a-web-service"></a>使用 .NET 代理服务连接到 Web 服务

如果您对要使用的 RPC/encoded Web 服务没有控制权，则可以创建一个 document/literal 代理 Microsoft .NET Web 服务，以便为要从 RPC/encoded Web 服务中调用的每个 Web 方法提供包装函数。然后，即可通过 InfoPath 使用代理 document/literal Web 服务。
  
.NET Framework 代码可以处理任何种类的 Web 服务（RPC/encoded 和 document/literal 均可），并且所有 .NET Web 服务都采用 document/literal 样式和编码。由于 .NET Framework 可以与任何种类的 Web 服务通信，因此您可以创建一个 .NET Web 服务，让该服务的方法调用 RPC/encoded Web 服务。.NET Web 服务将充当转换器的角色，以使 InfoPath 能够对 .NET Web 服务进行 document/literal 样式调用，而 .NET Web 服务反过来又可以对原始 Web 服务进行 RPC/encoded 样式调用。
  
创建此类代理 Microsoft .NET Web 服务的先决条件是有一台运行 Internet Information Services (IIS) 且安装了 ASP.NET 以部署代理 Web 服务的 Microsoft Windows 或 Microsoft Windows Server 计算机。在创建 InfoPath 解决方案时，您将会指向代理 Web 服务，而不是 RPC/encoded Web 服务。然后，代理 Web 服务会调用 RPC/encoded 服务。
  
## <a name="creating-a-proxy-web-service-using-visual-studio"></a>使用 Visual Studio 创建代理 Web 服务

1. 创建新的 **ASP.NET Web 服务应用程序**项目。 
    
2. 在****“解决方案资源管理器”中，右键单击新项目的“引用”**** 文件夹，然后单击“添加 Web 引用”****。 
    
3. 在“添加 Web 引用”**** 对话框中，键入要使用的 RPC/encoded Web 服务的 URL，然后单击“开始”****。
    
4. 单击“添加引用”****。 
    
5. 打开 Web 服务的 .asmx 文件，并添加一个 Web 服务方法，以便从引用的 RPC/encoded Web 服务调用每种 Web 服务方法。
    
6. To view a list of the methods in the reference RPC/encoded Web server, display the **Class View** window. For each Web Service method, you will see three methods. For example, if the Web Service method is called  `doSearch`, then you will see three methods called  `doSearch`,  `BegindoSearch`, and  `EnddoSearch`. You only have to create a wrapper Web Service method for the  `doSearch` method. Be sure to match the exact method signature and return type. 
    
7. 在每个包装方法中，您必须编写代码，以调用引用的 RPC/encoded Web 服务，如下例所示。 
    
   ```cs
    [WebMethod] 
    public string[] doSearch(string keyword) 
    { 
        SearchService srch = new SearchService(); 
        return srch.doSearch(keyword); 
    } 
    
   ```

8. 如果 RPC/encoded Web 服务需要身份验证，您可以将连接到 RPC/encoded 服务所需的凭据硬编码到代理 .NET Web 服务的源代码中，或者使用类似以下示例的代码。 
    
   ```cs
    myProxy.Credentials = System.Net.CredentialCache.DefaultCredentials; 
    
   ```

有关详细信息，请在 https://support.microsoft.com/ 上搜索 Microsoft 知识库文章"如何：将当前凭据传递给 ASP.NET Web 服务"。
    
## <a name="creating-a-proxy-web-service-without-visual-studio-net"></a>在不使用 Visual Studio .NET 的情况下创建代理 Web 服务

或者，您也可以使用随 .NET Framework 软件开发工具包（可从 MSDN 下载）提供的工具创建代理 Web 服务。
  
使用 Web Services 描述语言工具 (Wsdl.exe) 为代理 Web 服务创建代码文件。可以使用 .NET Framework SDK 随附的 C# 命令行编译器 (csc.exe) 或 Visual Basic .NET 命令行编译器 (vbc.exe) 来编译该代码文件。在 Web Services 描述语言工具生成代码文件后，将文件扩展名更改为 .asmx，然后在任意文本编辑器中打开该文件。在文档的第一行，添加以下页面指令：
  
```cs
<%@ WebService Language="C#" class="GoogleSearchServiceWrapper" %> 
```

转到代码文件的结尾并创建对 RPC/encoded Web 服务中每个 Web 服务方法的调用。以下代码示例演示了连接到 Google Web 服务（使用 RPC/encoded 样式进行开发）的 .NET Web 服务的代码。其中有一个占位符，用于放置 wsdl.exe 生成的代码。
  
```cs
<%@ WebService Language="C#" class="GoogleSearchServiceWrapper" %> 
 
using System; 
using System.Web.Services; 
 
// The auto-generated code from the wsdl.exe tool goes here. 
 
[WebService] 
public class GoogleSearchServiceWrapper : System.Web.Services.WebService  
{ 
    [WebMethod] 
    public System.Byte[] doGetCachedPage(System.String key, System.String url) 
    { 
        GoogleSearchService srch = new GoogleSearchService(); 
        return srch.doGetCachedPage(key, url); 
    } 
 
    [WebMethod] 
    public System.String doSpellingSuggestion(System.String key, System.String phrase) 
    { 
        GoogleSearchService srch = new GoogleSearchService(); 
        return srch.doSpellingSuggestion(key, phrase); 
    } 
 
    [WebMethod] 
    public GoogleSearchResult doGoogleSearch(System.String key, 
      System.String q, 
      System.Int32 start, 
      System.Int32 maxResults, 
      System.Boolean filter, 
      System.String restrict, 
      System.Boolean safeSearch, 
      System.String lr, 
      System.String ie, 
      System.String oe) 
    {
        GoogleSearchService srch = new GoogleSearchService();
           return srch.doGoogleSearch(key, q, start, maxResults, 
               filter, restrict, safeSearch, lr, ie, oe); 
    } 
}
```


