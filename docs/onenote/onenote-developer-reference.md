---
title: OneNote 开发人员参考
manager: soliver
ms.date: 05/16/2016
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4c4ef9e8-6b30-481b-8023-2e1280bcbcc9
description: 本参考包含概念概述和编程参考以指导您开发解决方案的 OneNote 2013 桌面客户端应用程序。
ms.openlocfilehash: 8af3f0b8623f0b457250ea11f185a25cadec7386
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774160"
---
# <a name="onenote-developer-reference"></a><span data-ttu-id="ab33e-103">OneNote 开发人员参考</span><span class="sxs-lookup"><span data-stu-id="ab33e-103">OneNote developer reference</span></span>

<span data-ttu-id="ab33e-104">本参考包含概念概述和编程参考以指导您开发解决方案的 OneNote 2013 桌面客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ab33e-104">This reference contains conceptual overviews and programmatic references to guide you in developing solutions for OneNote 2013 desktop client applications.</span></span> <span data-ttu-id="ab33e-105">它包括所有新增功能和更改为 OneNote 2013 应用程序编程接口 (API)，并提供在 C# 中以演示如何在 OneNote 中执行一些任务的代码示例。</span><span class="sxs-lookup"><span data-stu-id="ab33e-105">It includes all the additions and changes to the OneNote 2013 application programming interface (API), and provides code samples in C# to show how to perform some tasks in OneNote.</span></span> <span data-ttu-id="ab33e-106">OneNote 2013 API 使用户能够以编程方式访问和编辑 OneNote 内容。</span><span class="sxs-lookup"><span data-stu-id="ab33e-106">The OneNote 2013 API enables users to programmatically access and edit OneNote content.</span></span> <span data-ttu-id="ab33e-107">用户还可以为 OneNote 窗口的视图中进行更改。</span><span class="sxs-lookup"><span data-stu-id="ab33e-107">Users can also make changes to the view of OneNote windows.</span></span>
  
<span data-ttu-id="ab33e-108">本文档包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="ab33e-108">This documentation contains the following information:</span></span>
  
- <span data-ttu-id="ab33e-109">[Window 接口](window-interfaces-onenote.md)： 介绍**窗口**和**Windows**接口，使用户能够通过 OneNote 窗口的枚举和修改某些窗口属性。</span><span class="sxs-lookup"><span data-stu-id="ab33e-109">[Window interfaces](window-interfaces-onenote.md): Describes the **Window** and **Windows** interfaces, which enable users to enumerate through the set of OneNote windows and modify certain window properties.</span></span> 
    
- <span data-ttu-id="ab33e-110">[快速归档对话框框接口](quick-filing-dialog-box-interfaces-onenote.md)： 描述可用于以编程方式自定义 OneNote 2013 中的**快速归档**对话框的接口。</span><span class="sxs-lookup"><span data-stu-id="ab33e-110">[Quick Filing dialog box interfaces](quick-filing-dialog-box-interfaces-onenote.md): Describes the interfaces that you can use to programmatically customize the **Quick Filing** dialog box in OneNote 2013.</span></span> 
    
- <span data-ttu-id="ab33e-111">[应用程序界面](application-interface-onenote.md)： 描述方法、 属性和帮助检索、 操作和更新 OneNote 2013 信息和内容的事件。</span><span class="sxs-lookup"><span data-stu-id="ab33e-111">[Application interface](application-interface-onenote.md): Describes methods, properties, and events that help retrieve, manipulate, and update OneNote 2013 information and content.</span></span>
    
- <span data-ttu-id="ab33e-112">[枚举](enumerations-onenote-developer-reference.md)： 描述 OneNote 2013 对象模型中的枚举。</span><span class="sxs-lookup"><span data-stu-id="ab33e-112">[Enumerations](enumerations-onenote-developer-reference.md): Describes the enumerations in the OneNote 2013 object model.</span></span>
    
- <span data-ttu-id="ab33e-113">[错误代码](error-codes-onenote.md)： 列出了 OneNote 2013 对象模型中的错误代码。</span><span class="sxs-lookup"><span data-stu-id="ab33e-113">[Error codes](error-codes-onenote.md): Lists the error codes in the OneNote 2013 object model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab33e-p102">[!注释] 本文档中描述的 API 仅用于创建未连接方案中的 OneNote Win32 桌面客户端解决方案。对于已连接方案，请使用推荐的 OneNote 服务 API。要了解详细信息，请访问 [dev.onenote.com](http://go.microsoft.com/fwlink/?LinkID=390615)。</span><span class="sxs-lookup"><span data-stu-id="ab33e-p102">The APIs described in this documentation are intended only for OneNote Win32 desktop client solutions in unconnected scenarios. For connected scenarios, use the recommended OneNote service APIs. To learn more, visit [dev.onenote.com](http://go.microsoft.com/fwlink/?LinkID=390615).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ab33e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab33e-117">See also</span></span>

- [<span data-ttu-id="ab33e-118">面向开发人员的 OneNote</span><span class="sxs-lookup"><span data-stu-id="ab33e-118">OneNote for developers</span></span>](http://go.microsoft.com/fwlink/?LinkID=390615)
    
- <span data-ttu-id="ab33e-119">[GitHub 示例](https://github.com/OneNoteDev/)（OneNote 服务 Api）</span><span class="sxs-lookup"><span data-stu-id="ab33e-119">[Samples on GitHub](https://github.com/OneNoteDev/) (OneNote service APIs)</span></span> 
    
- [<span data-ttu-id="ab33e-120">Microsoft 产品中的辅助功能</span><span class="sxs-lookup"><span data-stu-id="ab33e-120">Accessibility in Microsoft Products</span></span>](http://www.microsoft.com/enable/products/default.aspx)
    
- [<span data-ttu-id="ab33e-121">文档约定</span><span class="sxs-lookup"><span data-stu-id="ab33e-121">Document Conventions</span></span>](http://msdn.microsoft.com/en-us/office/aa905365.aspx)
    
- [<span data-ttu-id="ab33e-122">OneNote 开发人员参考版权信息</span><span class="sxs-lookup"><span data-stu-id="ab33e-122">OneNote Developer Reference Copyright Information</span></span>](https://msdn.microsoft.com/en-us/library/office/jj680116.aspx)
    
- [<span data-ttu-id="ab33e-123">Microsoft Online 隐私声明</span><span class="sxs-lookup"><span data-stu-id="ab33e-123">Microsoft Online Privacy Notice</span></span>](http://privacy.microsoft.com/en-us/default.mspx)
    

