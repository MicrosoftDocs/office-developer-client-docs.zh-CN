---
title: OLE DB Provider for Internet Publishing
TOCTitle: The OLE DB Provider for Internet Publishing
ms:assetid: 864e5ece-0f50-5d88-4c40-f951b2a2eded
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249583(v=office.15)
ms:contentKeyID: 48546082
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3025637cf972f720db0a91b598d5903f13b8c9c4
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886961"
---
# <a name="the-ole-db-provider-for-internet-publishing"></a><span data-ttu-id="fecec-102">OLE DB Provider for Internet Publishing</span><span class="sxs-lookup"><span data-stu-id="fecec-102">The OLE DB Provider for Internet Publishing</span></span>


<span data-ttu-id="fecec-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fecec-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fecec-104">ADO [Record](record-object-ado.md)和[Stream](stream-object-ado.md)对象可用于 Microsoft OLE DB Provider for Internet Publishing (Internet Publishing Provider) 来访问和处理资源，如 web 文件夹或由 Microsoft FrontPage 的文件。</span><span class="sxs-lookup"><span data-stu-id="fecec-104">The ADO [Record](record-object-ado.md) and [Stream](stream-object-ado.md) objects can be used with the Microsoft OLE DB Provider for Internet Publishing (Internet Publishing Provider) to access and manipulate resources, such as web folders or files served by Microsoft FrontPage.</span></span> <span data-ttu-id="fecec-105">使用 ADO，可以指定要成为 URL 的 **Record** 、 **Stream** 或 [Recordset](recordset-object-ado.md) 的源。</span><span class="sxs-lookup"><span data-stu-id="fecec-105">With ADO, you can specify the source of a **Record**, **Stream**, or [Recordset](recordset-object-ado.md) to be a URL.</span></span> <span data-ttu-id="fecec-106">然后，可以上载、下载、移动、复制和删除资源，或者直接操作资源属性。</span><span class="sxs-lookup"><span data-stu-id="fecec-106">You can then upload, download, move, copy, and delete resources, or directly manipulate resource properties.</span></span>

<span data-ttu-id="fecec-107">有关将 **Records** 和 **Streams** 与 Internet Publishing Provider 一起使用的示例代码，请参阅 [Internet Publishing 方案](internet-publishing-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="fecec-107">For example code using **Records** and **Streams** with the Internet Publishing Provider, see the [Internet Publishing Scenario](internet-publishing-scenario.md).</span></span>

<span data-ttu-id="fecec-p102">Internet Publishing Provider 随 Microsoft Windows 2000 一起安装。早期版本的 Internet Publishing Provider 还可通过 Microsoft Office 2000 和 Microsoft Internet Explorer 5.0 来使用。</span><span class="sxs-lookup"><span data-stu-id="fecec-p102">The Internet Publishing Provider is installed with Microsoft Windows 2000. Earlier versions of the Internet Publishing Provider are also available with Microsoft Office 2000 and Microsoft Internet Explorer 5.0.</span></span>

<span data-ttu-id="fecec-110">可通过三种方法来将 ADO 连接到 Internet Publishing Provider：</span><span class="sxs-lookup"><span data-stu-id="fecec-110">There are three ways to connect ADO to the Internet Publishing Provider:</span></span>

- <span data-ttu-id="fecec-p103">在连接字符串中指定"URL="。例如：</span><span class="sxs-lookup"><span data-stu-id="fecec-p103">Specify "URL=" in the connection string. For example:</span></span>
    
  ```vb 
     
    objConn.Open "URL=https://servername" 
  ```

- <span data-ttu-id="fecec-113">指定的连接字符串的*提供程序*关键字 Msdaipp.dso。</span><span class="sxs-lookup"><span data-stu-id="fecec-113">Specify Msdaipp.dso for the *Provider* keyword of the connection string.</span></span> <span data-ttu-id="fecec-114">例如：</span><span class="sxs-lookup"><span data-stu-id="fecec-114">For example:</span></span>
    
  ```vb 
     
    objConn.Open "provider=MSDAIPP.DSO;data source=https://servername" 
  ```

- <span data-ttu-id="fecec-p105">为 [Connection](provider-property-ado.md) 对象的 [Provider](connection-object-ado.md) 属性指定 Msdaipp.dso。例如：</span><span class="sxs-lookup"><span data-stu-id="fecec-p105">Specify Msdaipp.dso for the [Provider](provider-property-ado.md) property of the [Connection](connection-object-ado.md) object. For example:</span></span>
    
  ```vb 
     
    objConn.Provider = "MSDAIPP.DSO" 
    objConn.Open "https://servername" 
  ```


> [!NOTE]
> <P><span data-ttu-id="fecec-117">如果 Msdaipp.dso 显式指定的提供程序，使用<EM>提供程序</EM>的连接字符串关键字或<STRONG>Provider</STRONG>属性，值为您不能使用"URL ="连接字符串中。</span><span class="sxs-lookup"><span data-stu-id="fecec-117">If Msdaipp.dso is explicitly specified as the value of the provider, either with the <EM>Provider</EM> connection string keyword or the <STRONG>Provider</STRONG> property, you cannot use "URL=" in the connection string.</span></span> <span data-ttu-id="fecec-118">否则，将会发生错误。</span><span class="sxs-lookup"><span data-stu-id="fecec-118">If you do, an error will occur.</span></span> <span data-ttu-id="fecec-119">如上所示相反，只需指定的 URL。</span><span class="sxs-lookup"><span data-stu-id="fecec-119">Instead, simply specify the URL as shown above.</span></span></P>



<span data-ttu-id="fecec-120">有关 Internet Publishing Provider 的更具体信息，请参阅 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)，也可以参阅随源应用程序提供的提供程序文档。源应用程序是指随其一起安装 OLE DB Provider for Internet Publishing 的应用程序，如 Windows 2000、Office 2000 或 Internet Explorer 5.0。</span><span class="sxs-lookup"><span data-stu-id="fecec-120">For more specific information about the Internet Publishing Provider, see [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md), or the provider documentation provided with the source application with which the OLE DB Provider for Internet Publishing was installed: Windows 2000, Office 2000, or Internet Explorer 5.0.</span></span>

