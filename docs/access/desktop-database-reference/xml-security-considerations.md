---
title: XML 安全考虑事项
TOCTitle: XML Security Considerations
ms:assetid: ef2c7f59-f5a2-98d1-37c6-42cb35b26a40
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250214(v=office.15)
ms:contentKeyID: 48548575
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 69672b2993cb91ace5bd447b762f33fcbd66c1bc
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868488"
---
# <a name="xml-security-considerations"></a><span data-ttu-id="21075-102">XML 安全考虑事项</span><span class="sxs-lookup"><span data-stu-id="21075-102">XML Security Considerations</span></span>


<span data-ttu-id="21075-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="21075-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="xml-security-considerations"></a><span data-ttu-id="21075-104">XML 安全考虑事项</span><span class="sxs-lookup"><span data-stu-id="21075-104">XML Security Considerations</span></span>

<span data-ttu-id="21075-p101">当在 Internet Explorer 中运行时， **Recordset** 对象的 ADO **Save** 和 **Open** 方法被视为不安全的操作。因此，如果使用这些方法的脚本代码在浏览器所宿主的应用程序或控件中运行，则该脚本代码的行为会受到浏览器安全配置的影响。</span><span class="sxs-lookup"><span data-stu-id="21075-p101">The ADO **Save** and **Open** methods on the **Recordset** object are not considered safe operations to run in Internet Explorer. Thus, if these methods are used in a script code that is running in an application or control that is hosted in a browser, the security configuration of the browser will have an effect on its behavior.</span></span>

<span data-ttu-id="21075-p102">默认情况下，Internet Explorer 5 在 Internet 区域中为这样的操作提供安全限制。在该配置下， **Recordset** 不能访问客户端上的本地文件系统，也不能访问下载页面的服务器的域外部的任何数据源。特别是，当在浏览器主机内部运行时，只有当下载页面的服务器与浏览器主机为同一服务器时， **Recordset** 才能重新保存到文件中。同样，只有文件位于下载页面的同一台服务器上时，才能从文件加载 **Recordset** 来打开它。</span><span class="sxs-lookup"><span data-stu-id="21075-p102">Internet Explorer 5 provides security restrictions for such operations by default in the Internet zones. Under that configuration, the **Recordset** cannot make any access to the local file system on the client or access any data sources outside the domain of the server from which the page has been downloaded. Specifically, when running inside the browser host, a **Recordset** can be saved back to a file only if it is on the same server from which the page was downloaded. Similarly, you can open a **Recordset** by loading it from a file only if that file is on the same server from which the page was downloaded.</span></span>

<span data-ttu-id="21075-111">有关 Internet Explorer 中安全性的详细信息，请参阅技术文章"Microsoft Internet Explorer 中的 ADO 和 RDS 安全问题"。</span><span class="sxs-lookup"><span data-stu-id="21075-111">For more information about security in Internet Explorer, see the technical article "ADO and RDS Security Issues in Microsoft Internet Explorer."</span></span>

