---
title: MAPI 表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 41d35370-495d-40fe-80bc-6c3bfc995b85
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b53cdb4fe379405018555f1cca9fa40ddc5d0fa8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592484"
---
# <a name="mapi-forms"></a><span data-ttu-id="54d86-103">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="54d86-103">MAPI Forms</span></span>

  
  
<span data-ttu-id="54d86-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="54d86-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="54d86-105">阅读此概述 MAPI 表单体系结构之后, 将具有了解什么是 MAPI 表单以及与其他组件的 MAPI 子系统交互的方式。</span><span class="sxs-lookup"><span data-stu-id="54d86-105">After reading this overview of the MAPI form architecture, you will have an understanding of what MAPI forms are and how they interact with other components of the MAPI subsystem.</span></span> <span data-ttu-id="54d86-106">本节旨在为您提供的概念的知识，您需要实现您自己的 MAPI 表单服务器。</span><span class="sxs-lookup"><span data-stu-id="54d86-106">The purpose of this section is to give you the conceptual knowledge you need to implement your own MAPI form servers.</span></span>
  
<span data-ttu-id="54d86-107">在之前阅读本节，您应熟悉的[MAPI 表单概述](mapi-forms-overview.md)主题中的材料。</span><span class="sxs-lookup"><span data-stu-id="54d86-107">Before reading this section, you should familiarize yourself with the material in the [MAPI Forms Overview](mapi-forms-overview.md) topic.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="54d86-108">MAPI 表单体系结构基于上组件对象模型 (COM)，因为开发表单服务器应用程序需要 COM 编程的知识。</span><span class="sxs-lookup"><span data-stu-id="54d86-108">Because the MAPI form architecture is based on the Component Object Model (COM), developing form server applications requires knowledge of COM programming.</span></span> <span data-ttu-id="54d86-109">有关 COM 的详细信息，请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务一节。</span><span class="sxs-lookup"><span data-stu-id="54d86-109">For more information about COM, see the COM and ActiveX Object Services section in the Windows SDK.</span></span> 
  

