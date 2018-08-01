---
title: 显示“常用地址”对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 276f9fa8-c333-4381-b20f-22fe9d2f27cd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a7b603504956be9ec3066e5ff5e1d5db7d59852a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774830"
---
# <a name="displaying-the-common-address-dialog-box"></a><span data-ttu-id="7f208-103">显示“常用地址”对话框</span><span class="sxs-lookup"><span data-stu-id="7f208-103">Displaying the Common Address Dialog Box</span></span>

  
  
<span data-ttu-id="7f208-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7f208-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7f208-105">MAPI 常见地址对话框中可用于各种寻址的任务，如构建收件人列表。</span><span class="sxs-lookup"><span data-stu-id="7f208-105">The MAPI common address dialog box can be used for a variety of addressing tasks such as constructing a recipient list.</span></span> <span data-ttu-id="7f208-106">若要显示此对话框中，调用**IAddrBook::Address**。</span><span class="sxs-lookup"><span data-stu-id="7f208-106">To display this dialog box, call **IAddrBook::Address**.</span></span> <span data-ttu-id="7f208-107">根据您设置的许多参数和如何设置，您可以从特定的容器，您显示对特定类型的条目限制。</span><span class="sxs-lookup"><span data-stu-id="7f208-107">Depending on which of the many parameters you set and how you set them, you can limit your display to entries of a particular type from a particular container.</span></span>
  
 <span data-ttu-id="7f208-108">**若要限制到显示个人通讯簿 (PAB) 条目地址对话框**</span><span class="sxs-lookup"><span data-stu-id="7f208-108">**To limit the address dialog box to displaying personal address book (PAB) entries only**</span></span>
  
1. <span data-ttu-id="7f208-109">调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。</span><span class="sxs-lookup"><span data-stu-id="7f208-109">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the entry identifier of the PAB.</span></span> 
    
2. <span data-ttu-id="7f208-110">创建作为[SPropertyRestriction](spropertyrestriction.md)结构和**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 的**relop**成员使用 RELOP_EQ 属性限制**ulPropTag**成员。</span><span class="sxs-lookup"><span data-stu-id="7f208-110">Create a property restriction that uses RELOP_EQ for the **relop** member of the [SPropertyRestriction](spropertyrestriction.md) structure and either **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) or **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) as the **ulPropTag** member.</span></span> <span data-ttu-id="7f208-111">如果您使用**PR_ENTRYID**，通过从**GetPAB**检索的项标识符。</span><span class="sxs-lookup"><span data-stu-id="7f208-111">If you use **PR_ENTRYID**, pass the entry identifier retrieved from **GetPAB**.</span></span> <span data-ttu-id="7f208-112">如果您使用**PR_AB_PROVIDER_ID**，传递 MSPAB 中包含的值。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="7f208-112">If you use **PR_AB_PROVIDER_ID**, pass the value included in the MSPAB.H header file.</span></span> <span data-ttu-id="7f208-113">**PR_AB_PROVIDER_ID**是 PAB 设计的 MAPI 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7f208-113">**PR_AB_PROVIDER_ID** is the unique identifier for the PAB designed by MAPI.</span></span> 
    
3. <span data-ttu-id="7f208-114">使用指向属性限制_lpHierRestriction_参数调用[IAddrBook::Address](iaddrbook-address.md) 。</span><span class="sxs-lookup"><span data-stu-id="7f208-114">Call [IAddrBook::Address](iaddrbook-address.md) with the  _lpHierRestriction_ parameter pointing to the property restriction.</span></span> 
    

