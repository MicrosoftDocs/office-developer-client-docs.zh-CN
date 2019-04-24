---
title: MAPI 表单
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 41d35370-495d-40fe-80bc-6c3bfc995b85
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 951a1c88d2fd4291ee0b48924de6eda8f43c3e47
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351343"
---
# <a name="mapi-forms"></a><span data-ttu-id="95c7e-103">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="95c7e-103">MAPI Forms</span></span>

  
  
<span data-ttu-id="95c7e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95c7e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95c7e-105">阅读 mapi 表单体系结构的此概述之后, 您将了解 mapi 表单是什么以及它们如何与 mapi 子系统的其他组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="95c7e-105">After reading this overview of the MAPI form architecture, you will have an understanding of what MAPI forms are and how they interact with other components of the MAPI subsystem.</span></span> <span data-ttu-id="95c7e-106">本节旨在为您提供实现您自己的 MAPI 表单服务器所需的概念性知识。</span><span class="sxs-lookup"><span data-stu-id="95c7e-106">The purpose of this section is to give you the conceptual knowledge you need to implement your own MAPI form servers.</span></span>
  
<span data-ttu-id="95c7e-107">阅读本部分之前, 应熟悉[MAPI 表单概述](mapi-forms-overview.md)主题中的资料。</span><span class="sxs-lookup"><span data-stu-id="95c7e-107">Before reading this section, you should familiarize yourself with the material in the [MAPI Forms Overview](mapi-forms-overview.md) topic.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="95c7e-108">由于 MAPI 表单体系结构基于组件对象模型 (COM), 因此开发表单服务器应用程序需要了解 COM 编程。</span><span class="sxs-lookup"><span data-stu-id="95c7e-108">Because the MAPI form architecture is based on the Component Object Model (COM), developing form server applications requires knowledge of COM programming.</span></span> <span data-ttu-id="95c7e-109">有关 COM 的详细信息, 请参阅 Windows SDK 中的 com 和 ActiveX 对象服务一节。</span><span class="sxs-lookup"><span data-stu-id="95c7e-109">For more information about COM, see the COM and ActiveX Object Services section in the Windows SDK.</span></span> 
  

