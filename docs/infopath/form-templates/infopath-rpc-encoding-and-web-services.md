---
title: InfoPath、RPC 编码和 Web 服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: f8d7b944-a8fd-9c5f-8f66-0f1b628b7c6e
description: Web 服务可以向描述 Web 服务的 Web 服务描述语言 (WSDL) 协定中的 Web 方法公开两种绑定样式中的一种：Document 或 RPC。
ms.openlocfilehash: 01b75df42bce97d62ebb5e273588cb522e5e2a09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774006"
---
# <a name="infopath-rpc-encoding-and-web-services"></a><span data-ttu-id="50ffb-103">InfoPath、RPC 编码和 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50ffb-103">InfoPath, RPC Encoding and Web Services</span></span>

<span data-ttu-id="50ffb-p101">Web 服务可以向描述 Web 服务的 Web 服务描述语言 (WSDL) 协定中的 Web 方法公开两种绑定样式中的一种：Document 或 RPC。此外，还可以将这两种绑定样式中的每一种分别指定为 literal 或 encoded。每种类型最常见的实施方法是：document/literal 和 RPC/encoded。但是，Microsoft InfoPath 只支持连接到使用 document/literal 样式的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p101">Web services can expose one of two styles for binding to their Web methods in the Web Service Description Language (WSDL) contract that describes them: Document or RPC. Additionally, each of these two styles of binding can be specified as either literal or encoded. The most common implementations for each type are: document/literal and RPC/encoded. However, Microsoft InfoPath only supports connecting to Web services that use the document/literal style.</span></span>
  
<span data-ttu-id="50ffb-p102">大多数 Web 服务开发工具都提供用于指定要创建的 Web 服务种类的开关。如果要开发将从 InfoPath 进行连接的 Web 服务，则应指定 document/literal 作为 Web 服务的样式和编码。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p102">Most Web service development tools provide a switch for specifying what kind of Web service that you want to create. If you are developing a Web service that you will be connecting to from InfoPath, you should specify document/literal as your Web service's style and encoding.</span></span>
  
<span data-ttu-id="50ffb-110">但是，如果您对要使用的 Web 服务没有控制权，并且必须连接到使用 RPC/encoded 样式的 Web 服务，则可以使用 .NET 代理服务连接到 RPC/encoded Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50ffb-110">However, if you do not control the Web service that you want to work with, and you must connect to a Web service uses the RPC/encoded style, you can use a .NET proxy service to connect to an RPC/encoded Web service.</span></span>
  
## <a name="using-a-net-proxy-service-to-connect-to-a-web-service"></a><span data-ttu-id="50ffb-111">使用 .NET 代理服务连接到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50ffb-111">Using a .NET Proxy Service to Connect to a Web Service</span></span>

<span data-ttu-id="50ffb-p103">如果您对要使用的 RPC/encoded Web 服务没有控制权，则可以创建一个 document/literal 代理 Microsoft .NET Web 服务，以便为要从 RPC/encoded Web 服务中调用的每个 Web 方法提供包装函数。然后，即可通过 InfoPath 使用代理 document/literal Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p103">If you do not control the RPC/encoded Web service that you want to work with, you can create a document/literal proxy Microsoft .NET Web service that provides wrapper functions for each of the Web methods, you want to invoke from the RPC/encoded Web service. You can then work with the proxy document/literal Web service from InfoPath.</span></span>
  
<span data-ttu-id="50ffb-p104">.NET Framework 代码可以处理任何种类的 Web 服务（RPC/encoded 和 document/literal 均可），并且所有 .NET Web 服务都采用 document/literal 样式和编码。由于 .NET Framework 可以与任何种类的 Web 服务通信，因此您可以创建一个 .NET Web 服务，让该服务的方法调用 RPC/encoded Web 服务。.NET Web 服务将充当转换器的角色，以使 InfoPath 能够对 .NET Web 服务进行 document/literal 样式调用，而 .NET Web 服务反过来又可以对原始 Web 服务进行 RPC/encoded 样式调用。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p104">.NET Framework code can work with any kind of Web service (both RPC/encoded and document/literal), and all .NET Web services use the document/literal style and encoding. Because the .NET Framework can communicate with any kind of Web service, you can create a .NET Web service that has methods that make calls to the RPC/encoded Web service. The .NET Web service will act as a translator that enables InfoPath to make document/literal style calls to the .NET Web service which in turn can make RPC/encoded style calls to the original Web service.</span></span>
  
<span data-ttu-id="50ffb-p105">创建此类代理 Microsoft .NET Web 服务的先决条件是有一台运行 Internet Information Services (IIS) 且安装了 ASP.NET 以部署代理 Web 服务的 Microsoft Windows 或 Microsoft Windows Server 计算机。在创建 InfoPath 解决方案时，您将会指向代理 Web 服务，而不是 RPC/encoded Web 服务。然后，代理 Web 服务会调用 RPC/encoded 服务。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p105">The prerequisites for creating such a proxy Microsoft .NET Web service are a Microsoft Windows or Microsoft Windows Server computer that is running Internet Information Services (IIS) with ASP.NET installed on which to deploy the proxy Web service. When you create an InfoPath solution, you will point to the proxy Web service instead of the RPC/encoded Web service. The proxy Web service will then make calls to the RPC/encoded service.</span></span>
  
## <a name="creating-a-proxy-web-service-using-visual-studio"></a><span data-ttu-id="50ffb-120">使用 Visual Studio 创建代理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50ffb-120">Creating a Proxy Web Service Using Visual Studio</span></span>

1. <span data-ttu-id="50ffb-121">创建新的 **ASP.NET Web 服务应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="50ffb-121">Create a new **ASP.NET Web Service Application** project.</span></span> 
    
2. <span data-ttu-id="50ffb-122">在****“解决方案资源管理器”中，右键单击新项目的“引用”**** 文件夹，然后单击“添加 Web 引用”****。</span><span class="sxs-lookup"><span data-stu-id="50ffb-122">In the **Solution Explorer**, right-click the **References** folder of your new project, and then click **Add Web Reference**.</span></span> 
    
3. <span data-ttu-id="50ffb-123">在“添加 Web 引用”**** 对话框中，键入要使用的 RPC/encoded Web 服务的 URL，然后单击“开始”****。</span><span class="sxs-lookup"><span data-stu-id="50ffb-123">In the **Add Web Reference** dialog box, type in the URL of the RPC/encoded Web service that you want to work with, and then click **Go**.</span></span>
    
4. <span data-ttu-id="50ffb-124">单击“添加引用”****。</span><span class="sxs-lookup"><span data-stu-id="50ffb-124">Click **Add Reference**.</span></span> 
    
5. <span data-ttu-id="50ffb-125">打开 Web 服务的 .asmx 文件，并添加一个 Web 服务方法，以便从引用的 RPC/encoded Web 服务调用每种 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="50ffb-125">Open the .asmx file for your Web service and add one Web Service method to call each Web Service method from the referenced RPC/encoded Web service.</span></span>
    
6. <span data-ttu-id="50ffb-126">要在引用 RPC/已编码 Web 服务器中查看方法列表，请显示****“类视图”窗口。</span><span class="sxs-lookup"><span data-stu-id="50ffb-126">To view a list of the methods in the reference RPC/encoded Web server, display the **Class View** window.</span></span> <span data-ttu-id="50ffb-127">对于每个 Web 服务方法，你将看到三个方法。</span><span class="sxs-lookup"><span data-stu-id="50ffb-127">For each Web Service method, you will see three methods.</span></span> <span data-ttu-id="50ffb-128">例如，如果 Web 服务方法称为 `doSearch`，则你将看到分别称为 `doSearch`、`BegindoSearch` 和 `EnddoSearch` 的三个方法。</span><span class="sxs-lookup"><span data-stu-id="50ffb-128">For example, if the Web Service method is called  `doSearch`, then you will see three methods called  `doSearch`,  `BegindoSearch`, and  `EnddoSearch`.</span></span> <span data-ttu-id="50ffb-129">只需为 `doSearch` 方法创建包装 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="50ffb-129">You only have to create a wrapper Web Service method for the  `doSearch` method.</span></span> <span data-ttu-id="50ffb-130">请务必匹配确切的方法签名和返回类型。</span><span class="sxs-lookup"><span data-stu-id="50ffb-130">Be sure to match the exact method signature and return type.</span></span> 
    
7. <span data-ttu-id="50ffb-131">在每个包装方法中，您必须编写代码，以调用引用的 RPC/encoded Web 服务，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="50ffb-131">Within each wrapper method, you have to write code to make a call to the referenced RPC/encoded Web service as shown in the following example.</span></span> 
    
   ```cs
    [WebMethod] 
    public string[] doSearch(string keyword) 
    { 
        SearchService srch = new SearchService(); 
        return srch.doSearch(keyword); 
    } 
    
   ```

8. <span data-ttu-id="50ffb-132">如果 RPC/encoded Web 服务需要身份验证，您可以将连接到 RPC/encoded 服务所需的凭据硬编码到代理 .NET Web 服务的源代码中，或者使用类似以下示例的代码。</span><span class="sxs-lookup"><span data-stu-id="50ffb-132">If the RPC/encoded Web service requires authentication, you can hard code the credentials required to connect to the RPC/encoded Web service into the source code for the proxy .NET Web service, or you can use code like the following example.</span></span> 
    
   ```cs
    myProxy.Credentials = System.Net.CredentialCache.DefaultCredentials; 
    
   ```

<span data-ttu-id="50ffb-133">有关详细信息，请在 http://support.microsoft.com/ 上搜索 Microsoft 知识库文章"如何：将当前凭据传递给 ASP.NET Web 服务"。</span><span class="sxs-lookup"><span data-stu-id="50ffb-133">For more information, search for the Microsoft Knowledge Base article "HOW TO: Pass Current Credentials to an ASP.NET Web Service" on http://support.microsoft.com/.</span></span>
    
## <a name="creating-a-proxy-web-service-without-visual-studio-net"></a><span data-ttu-id="50ffb-134">在不使用 Visual Studio .NET 的情况下创建代理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="50ffb-134">Creating a Proxy Web Service Without Visual Studio .NET</span></span>

<span data-ttu-id="50ffb-135">或者，您也可以使用随 .NET Framework 软件开发工具包（可从 MSDN 下载）提供的工具创建代理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="50ffb-135">Alternatively, you can create a proxy Web service by using the tools that are provided with the .NET Framework Software Development Kit, which can be downloaded from MSDN.</span></span>
  
<span data-ttu-id="50ffb-p107">使用 Web Services 描述语言工具 (Wsdl.exe) 为代理 Web 服务创建代码文件。可以使用 .NET Framework SDK 随附的 C# 命令行编译器 (csc.exe) 或 Visual Basic .NET 命令行编译器 (vbc.exe) 来编译该代码文件。在 Web Services 描述语言工具生成代码文件后，将文件扩展名更改为 .asmx，然后在任意文本编辑器中打开该文件。在文档的第一行，添加以下页面指令：</span><span class="sxs-lookup"><span data-stu-id="50ffb-p107">Use the Web Services Description Language Tool (Wsdl.exe) to create the code file for your proxy Web service. This code file can be compiled by using the C# command-line compiler (csc.exe) or the Visual Basic .NET command-line compiler (vbc.exe), which are also included with the .NET Framework SDK. After the Web Services Description Language tool has generated the code file, rename the file name extension to .asmx and open the file in any text editor. On the very first line of the document, add the following page directive:</span></span>
  
```cs
<%@ WebService Language="C#" class="GoogleSearchServiceWrapper" %> 
```

<span data-ttu-id="50ffb-p108">转到代码文件的结尾并创建对 RPC/encoded Web 服务中每个 Web 服务方法的调用。以下代码示例演示了连接到 Google Web 服务（使用 RPC/encoded 样式进行开发）的 .NET Web 服务的代码。其中有一个占位符，用于放置 wsdl.exe 生成的代码。</span><span class="sxs-lookup"><span data-stu-id="50ffb-p108">Go to the end of the code file and create a call to each Web Service method in the RPC/encoded Web service. The following code sample shows the code for a .NET Web service that connects to the Google Web service, which uses the RPC/encoded style of development. There is a placeholder for where the wsdl.exe generated code should go.</span></span>
  
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


