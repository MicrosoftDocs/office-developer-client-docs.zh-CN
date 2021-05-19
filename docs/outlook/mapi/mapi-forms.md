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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409970"
---
# <a name="mapi-forms"></a><span data-ttu-id="eaf5d-103">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="eaf5d-103">MAPI Forms</span></span>

  
  
<span data-ttu-id="eaf5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eaf5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eaf5d-105">阅读 MAPI 表单体系结构的此概述后，您将了解什么是 MAPI 表单，以及这些表单如何与 MAPI 子系统的其他组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="eaf5d-105">After reading this overview of the MAPI form architecture, you will have an understanding of what MAPI forms are and how they interact with other components of the MAPI subsystem.</span></span> <span data-ttu-id="eaf5d-106">本节的目的是为您提供实现您自己的 MAPI 表单服务器所需的概念知识。</span><span class="sxs-lookup"><span data-stu-id="eaf5d-106">The purpose of this section is to give you the conceptual knowledge you need to implement your own MAPI form servers.</span></span>
  
<span data-ttu-id="eaf5d-107">在阅读本节之前，您应熟悉 [MAPI Forms Overview主题中的](mapi-forms-overview.md) 材料。</span><span class="sxs-lookup"><span data-stu-id="eaf5d-107">Before reading this section, you should familiarize yourself with the material in the [MAPI Forms Overview](mapi-forms-overview.md) topic.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eaf5d-108">由于 MAPI 表单体系结构基于组件对象模型 (COM) ，因此开发表单服务器应用程序需要了解 COM 编程知识。</span><span class="sxs-lookup"><span data-stu-id="eaf5d-108">Because the MAPI form architecture is based on the Component Object Model (COM), developing form server applications requires knowledge of COM programming.</span></span> <span data-ttu-id="eaf5d-109">有关 COM 详细信息，请参阅 WINDOWS SDK 中的 COM 和 ActiveX 对象服务部分。</span><span class="sxs-lookup"><span data-stu-id="eaf5d-109">For more information about COM, see the COM and ActiveX Object Services section in the Windows SDK.</span></span> 
  

