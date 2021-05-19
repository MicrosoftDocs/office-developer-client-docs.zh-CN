---
title: 开发 MAPI 表单服务器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 30672a2d-2d39-4292-b21a-97a38485d1de
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 63aa9db19c901f47004a7fe52d906846f44b8883
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420764"
---
# <a name="developing-mapi-form-servers"></a><span data-ttu-id="ba305-103">开发 MAPI 表单服务器</span><span class="sxs-lookup"><span data-stu-id="ba305-103">Developing MAPI Form Servers</span></span>

  
  
<span data-ttu-id="ba305-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba305-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba305-105">本节介绍创建表单服务器可执行文件和表单配置文件以创建自定义 MAPI 表单的过程。</span><span class="sxs-lookup"><span data-stu-id="ba305-105">This section describes the process of creating form server executable and form configuration files for creating custom MAPI forms.</span></span> <span data-ttu-id="ba305-106">在阅读本节之前，您应熟悉 [MAPI Forms 中的信息](mapi-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ba305-106">Before reading this section, you should familiarize yourself with the information in [MAPI Forms](mapi-forms.md).</span></span>
  
<span data-ttu-id="ba305-107">开发表单服务器包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ba305-107">Developing a form server includes the following steps:</span></span>
  
1. <span data-ttu-id="ba305-108">决定表单将包含哪些信息，并选择一组属性来保存该信息。</span><span class="sxs-lookup"><span data-stu-id="ba305-108">Deciding what information the form will contain and choosing a set of properties to hold that information.</span></span> <span data-ttu-id="ba305-109">有关详细信息，请参阅 [选择窗体的属性集](choosing-a-form-s-property-set.md)。</span><span class="sxs-lookup"><span data-stu-id="ba305-109">For more information, see [Choosing a Form's Property Set](choosing-a-form-s-property-set.md).</span></span>
    
2. <span data-ttu-id="ba305-110">设计用户可与表单属性进行交互的用户界面。</span><span class="sxs-lookup"><span data-stu-id="ba305-110">Designing a user interface with which users can interact with the form's properties.</span></span>
    
3. <span data-ttu-id="ba305-111">选择邮件类，并生成 CLSID (的唯) 。</span><span class="sxs-lookup"><span data-stu-id="ba305-111">Choosing a message class and generating a unique class identifier (CLSID).</span></span> <span data-ttu-id="ba305-112">有关邮件类的概述，请参阅[MAPI Message Classes。](mapi-message-classes.md)</span><span class="sxs-lookup"><span data-stu-id="ba305-112">For an overview of message classes, see [MAPI Message Classes](mapi-message-classes.md).</span></span> <span data-ttu-id="ba305-113">有关邮件类和窗体的信息，请参阅 [选择邮件类](choosing-a-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="ba305-113">For more information about message classes and forms, see [Choosing a Message Class](choosing-a-message-class.md).</span></span>
    
4. <span data-ttu-id="ba305-114">实现所需的 MAPI 表单接口，以及您的特定表单服务器需要的任何可选接口。</span><span class="sxs-lookup"><span data-stu-id="ba305-114">Implementing the required MAPI form interfaces, as well as any optional interfaces that your particular form server needs.</span></span> <span data-ttu-id="ba305-115">有关详细信息，请参阅编写 [表单服务器代码](writing-form-server-code.md)。</span><span class="sxs-lookup"><span data-stu-id="ba305-115">For more information, see [Writing Form Server Code](writing-form-server-code.md).</span></span> 
    
5. <span data-ttu-id="ba305-116">编写用户界面代码以处理用户与表单对象以及表单使用的属性的交互。</span><span class="sxs-lookup"><span data-stu-id="ba305-116">Writing user interface code to handle the user's interaction with the form object and the properties the form uses.</span></span>
    
6. <span data-ttu-id="ba305-117">为表单创建表单配置文件。</span><span class="sxs-lookup"><span data-stu-id="ba305-117">Creating a form configuration file for the form.</span></span> <span data-ttu-id="ba305-118">有关详细信息，请参阅[File Format of Form Configuration Files。](file-format-of-form-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="ba305-118">For more information, see [File Format of Form Configuration Files](file-format-of-form-configuration-files.md).</span></span>
    
7. <span data-ttu-id="ba305-119">在用户计算机上安装表单。</span><span class="sxs-lookup"><span data-stu-id="ba305-119">Installing the form on users' computers.</span></span> <span data-ttu-id="ba305-120">有关详细信息，请参阅 [将窗体安装到库中](installing-a-form-into-a-library.md)。</span><span class="sxs-lookup"><span data-stu-id="ba305-120">For more information, see [Installing a Form into a Library](installing-a-form-into-a-library.md).</span></span>
    
<span data-ttu-id="ba305-121">您很可能同时执行步骤 1 到步骤 5，而不是按顺序完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="ba305-121">You will most likely perform steps 1 through 5 simultaneously rather than completing them in sequence.</span></span> <span data-ttu-id="ba305-122">像许多编程项目一样，开发表单服务器的过程不是一个定义特别明确的顺序的过程。</span><span class="sxs-lookup"><span data-stu-id="ba305-122">The process of developing a form server, like many programming projects, is not one in which there is a particularly well-defined sequence.</span></span> <span data-ttu-id="ba305-123">例如，创建表单配置文件显示为上述第二步，但您可能以增量方式创建表单配置文件，当您向表单服务器添加功能时，该文件将变得更加完整。</span><span class="sxs-lookup"><span data-stu-id="ba305-123">For example, creating a form configuration file is shown as the second-to-last step above, but you will probably create your form configuration file incrementally, and it will become more complete as you add features to your form server.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba305-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba305-124">See also</span></span>



[<span data-ttu-id="ba305-125">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="ba305-125">MAPI Concepts</span></span>](mapi-concepts.md)

