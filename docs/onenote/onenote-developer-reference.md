---
title: OneNote 开发人员参考
manager: soliver
ms.date: 05/16/2016
ms.audience: Developer
ms.assetid: 4c4ef9e8-6b30-481b-8023-2e1280bcbcc9
description: 此参考包含概念性概述与编程参考，可指导开发 OneNote 2013 桌面客户端应用程序解决方案。
localization_priority: Priority
ms.openlocfilehash: d2b401a768e62c4b9712b1590bfaf499c2b022ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317050"
---
# <a name="onenote-developer-reference"></a><span data-ttu-id="a57e4-103">OneNote 开发人员参考</span><span class="sxs-lookup"><span data-stu-id="a57e4-103">OneNote developer reference</span></span>

<span data-ttu-id="a57e4-104">此参考包含概念性概述与编程参考，可指导开发 OneNote 2013 桌面客户端应用程序解决方案。</span><span class="sxs-lookup"><span data-stu-id="a57e4-104">This reference contains conceptual overviews and programmatic references to guide you in developing solutions for OneNote 2013 desktop client applications.</span></span> <span data-ttu-id="a57e4-105">它包含 OneNote 2013 应用程序编程接口 (API) 的所有添加和变更，并提供 C# 代码示例以展示如何在 OneNote 中执行某些任务。</span><span class="sxs-lookup"><span data-stu-id="a57e4-105">It includes all the additions and changes to the OneNote 2013 application programming interface (API), and provides code samples in C# to show how to perform some tasks in OneNote.</span></span> <span data-ttu-id="a57e4-106">OneNote 2013 API 使用户能够以编程方式访问和编辑 OneNote 内容。</span><span class="sxs-lookup"><span data-stu-id="a57e4-106">The OneNote 2013 API enables users to programmatically access and edit OneNote content.</span></span> <span data-ttu-id="a57e4-107">用户还可以对 OneNote 窗口视图进行更改。</span><span class="sxs-lookup"><span data-stu-id="a57e4-107">Users can also make changes to the view of OneNote windows.</span></span>
  
<span data-ttu-id="a57e4-108">本文档包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="a57e4-108">This documentation contains the following information:</span></span>
  
- <span data-ttu-id="a57e4-109">[窗口接口](window-interfaces-onenote.md)： 介绍“**窗口**”和“**多个窗口**”接口，使用户能够通过 OneNote 窗口组枚举和修改某些窗口属性。</span><span class="sxs-lookup"><span data-stu-id="a57e4-109">[Window interfaces](window-interfaces-onenote.md): Describes the **Window** and **Windows** interfaces, which enable users to enumerate through the set of OneNote windows and modify certain window properties.</span></span> 
    
- <span data-ttu-id="a57e4-110">[快速归档对话框接口](quick-filing-dialog-box-interfaces-onenote.md)：介绍可用于以编程方式自定义OneNote 2013 中“**快速归档**”对话框的接口。</span><span class="sxs-lookup"><span data-stu-id="a57e4-110">[Quick Filing dialog box interfaces](quick-filing-dialog-box-interfaces-onenote.md): Describes the interfaces that you can use to programmatically customize the **Quick Filing** dialog box in OneNote 2013.</span></span> 
    
- <span data-ttu-id="a57e4-111">[应用程序接口](application-interface-onenote.md)：介绍帮助检索、 操作和更新 OneNote 2013 信息和内容的方法、 属性和事件。</span><span class="sxs-lookup"><span data-stu-id="a57e4-111">[Application interface](application-interface-onenote.md): Describes methods, properties, and events that help retrieve, manipulate, and update OneNote 2013 information and content.</span></span>
    
- <span data-ttu-id="a57e4-112">[枚举](enumerations-onenote-developer-reference.md)： 介绍 OneNote 2013 对象模型中的枚举。</span><span class="sxs-lookup"><span data-stu-id="a57e4-112">[Enumerations](enumerations-onenote-developer-reference.md): Describes the enumerations in the OneNote 2013 object model.</span></span>
    
- <span data-ttu-id="a57e4-113">[错误代码](error-codes-onenote.md)：列出 OneNote 2013 对象模型中的错误代码。</span><span class="sxs-lookup"><span data-stu-id="a57e4-113">[Error codes](error-codes-onenote.md): Lists the error codes in the OneNote 2013 object model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a57e4-p102">[!注释] 本文档中描述的 API 仅用于创建未连接方案中的 OneNote Win32 桌面客户端解决方案。对于已连接方案，请使用推荐的 OneNote 服务 API。要了解详细信息，请访问 [dev.onenote.com](https://go.microsoft.com/fwlink/?LinkID=390615)。</span><span class="sxs-lookup"><span data-stu-id="a57e4-p102">The APIs described in this documentation are intended only for OneNote Win32 desktop client solutions in unconnected scenarios. For connected scenarios, use the recommended OneNote service APIs. To learn more, visit [dev.onenote.com](https://go.microsoft.com/fwlink/?LinkID=390615).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a57e4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a57e4-117">See also</span></span>

- [<span data-ttu-id="a57e4-118">面向开发人员的 OneNote</span><span class="sxs-lookup"><span data-stu-id="a57e4-118">OneNote for developers</span></span>](https://go.microsoft.com/fwlink/?LinkID=390615)   
- <span data-ttu-id="a57e4-119">[GitHub 取样](https://github.com/OneNoteDev/)（OneNote 服务 API）</span><span class="sxs-lookup"><span data-stu-id="a57e4-119">[Samples on GitHub](https://github.com/OneNoteDev/) (OneNote service APIs)</span></span>     
- [<span data-ttu-id="a57e4-120">Microsoft 产品中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="a57e4-120">Accessibility in Microsoft Products</span></span>](https://www.microsoft.com/enable/products/default.aspx)    
- [<span data-ttu-id="a57e4-121">文档约定</span><span class="sxs-lookup"><span data-stu-id="a57e4-121">Document Conventions</span></span>](https://msdn.microsoft.com/office/aa905365.aspx)    
- [<span data-ttu-id="a57e4-122">OneNote 开发人员参考版权信息</span><span class="sxs-lookup"><span data-stu-id="a57e4-122">OneNote Developer Reference Copyright Information</span></span>](https://msdn.microsoft.com/library/office/jj680116.aspx)
    
    

