---
title: 开发 MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30672a2d-2d39-4292-b21a-97a38485d1de
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d55134cf5181ebbba0108c228d9afc3a494e75ce
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576237"
---
# <a name="developing-mapi-form-servers"></a><span data-ttu-id="5f025-103">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="5f025-103">Developing MAPI Form Servers</span></span>

  
  
<span data-ttu-id="5f025-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f025-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f025-105">本节介绍创建窗体服务器可执行文件和用于创建自定义 MAPI 窗体的窗体配置文件的过程。</span><span class="sxs-lookup"><span data-stu-id="5f025-105">This section describes the process of creating form server executable and form configuration files for creating custom MAPI forms.</span></span> <span data-ttu-id="5f025-106">在之前阅读本节，您应熟悉[MAPI 窗体](mapi-forms.md)中的信息。</span><span class="sxs-lookup"><span data-stu-id="5f025-106">Before reading this section, you should familiarize yourself with the information in [MAPI Forms](mapi-forms.md).</span></span>
  
<span data-ttu-id="5f025-107">开发表单服务器包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5f025-107">Developing a form server includes the following steps:</span></span>
  
1. <span data-ttu-id="5f025-108">确定窗体将包含哪些信息，然后选择要保留的信息的属性集。</span><span class="sxs-lookup"><span data-stu-id="5f025-108">Deciding what information the form will contain and choosing a set of properties to hold that information.</span></span> <span data-ttu-id="5f025-109">有关详细信息，请参阅[Choosing 窗体的属性设置](choosing-a-form-s-property-set.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-109">For more information, see [Choosing a Form's Property Set](choosing-a-form-s-property-set.md).</span></span>
    
2. <span data-ttu-id="5f025-110">设计与，用户可以与窗体的属性进行交互的用户界面。</span><span class="sxs-lookup"><span data-stu-id="5f025-110">Designing a user interface with which users can interact with the form's properties.</span></span>
    
3. <span data-ttu-id="5f025-111">选择邮件类并生成的唯一的类标识符 (CLSID)。</span><span class="sxs-lookup"><span data-stu-id="5f025-111">Choosing a message class and generating a unique class identifier (CLSID).</span></span> <span data-ttu-id="5f025-112">邮件类的概述，请参阅[MAPI 邮件类](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-112">For an overview of message classes, see [MAPI Message Classes](mapi-message-classes.md).</span></span> <span data-ttu-id="5f025-113">有关邮件类和窗体的详细信息，请参阅[Choosing 邮件类](choosing-a-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-113">For more information about message classes and forms, see [Choosing a Message Class](choosing-a-message-class.md).</span></span>
    
4. <span data-ttu-id="5f025-114">实现所需的 MAPI 表单接口，以及特定窗体服务器需要的任何可选接口。</span><span class="sxs-lookup"><span data-stu-id="5f025-114">Implementing the required MAPI form interfaces, as well as any optional interfaces that your particular form server needs.</span></span> <span data-ttu-id="5f025-115">有关详细信息，请参阅[编写窗体服务器代码](writing-form-server-code.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-115">For more information, see [Writing Form Server Code](writing-form-server-code.md).</span></span> 
    
5. <span data-ttu-id="5f025-116">编写用户界面的代码来处理用户交互的 form 对象和属性使用窗体。</span><span class="sxs-lookup"><span data-stu-id="5f025-116">Writing user interface code to handle the user's interaction with the form object and the properties the form uses.</span></span>
    
6. <span data-ttu-id="5f025-117">创建窗体的窗体配置文件。</span><span class="sxs-lookup"><span data-stu-id="5f025-117">Creating a form configuration file for the form.</span></span> <span data-ttu-id="5f025-118">有关详细信息，请参阅[窗体配置文件的文件格式](file-format-of-form-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-118">For more information, see [File Format of Form Configuration Files](file-format-of-form-configuration-files.md).</span></span>
    
7. <span data-ttu-id="5f025-119">用户的计算机上安装窗体。</span><span class="sxs-lookup"><span data-stu-id="5f025-119">Installing the form on users' computers.</span></span> <span data-ttu-id="5f025-120">有关详细信息，请参阅[安装到库窗体](installing-a-form-into-a-library.md)。</span><span class="sxs-lookup"><span data-stu-id="5f025-120">For more information, see [Installing a Form into a Library](installing-a-form-into-a-library.md).</span></span>
    
<span data-ttu-id="5f025-121">您很可能将执行步骤 1 至 5 同时而不是从顺序完成它们。</span><span class="sxs-lookup"><span data-stu-id="5f025-121">You will most likely perform steps 1 through 5 simultaneously rather than completing them in sequence.</span></span> <span data-ttu-id="5f025-122">开发一个窗体服务器，许多编程项目，如过程不是一个处于特别是定义完善序列。</span><span class="sxs-lookup"><span data-stu-id="5f025-122">The process of developing a form server, like many programming projects, is not one in which there is a particularly well-defined sequence.</span></span> <span data-ttu-id="5f025-123">例如，创建窗体配置文件显示为第二个上次步骤，您可能将创建窗体配置文件增量，但它将变得更完整，您将功能添加到窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="5f025-123">For example, creating a form configuration file is shown as the second-to-last step above, but you will probably create your form configuration file incrementally, and it will become more complete as you add features to your form server.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f025-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f025-124">See also</span></span>



[<span data-ttu-id="5f025-125">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="5f025-125">MAPI Concepts</span></span>](mapi-concepts.md)

