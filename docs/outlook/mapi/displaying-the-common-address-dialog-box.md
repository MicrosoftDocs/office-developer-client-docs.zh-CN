---
title: 显示 "常用地址" 对话框
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 276f9fa8-c333-4381-b20f-22fe9d2f27cd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 812c850d1fcb6d3712d76b160b56b839b2e1353d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436901"
---
# <a name="displaying-the-common-address-dialog-box"></a><span data-ttu-id="736fb-103">显示 "常用地址" 对话框</span><span class="sxs-lookup"><span data-stu-id="736fb-103">Displaying the Common Address Dialog Box</span></span>

  
  
<span data-ttu-id="736fb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="736fb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="736fb-105">"MAPI 常用地址" 对话框可用于各种寻址任务, 如构造收件人列表。</span><span class="sxs-lookup"><span data-stu-id="736fb-105">The MAPI common address dialog box can be used for a variety of addressing tasks such as constructing a recipient list.</span></span> <span data-ttu-id="736fb-106">若要显示此对话框, 请调用**IAddrBook:: Address**。</span><span class="sxs-lookup"><span data-stu-id="736fb-106">To display this dialog box, call **IAddrBook::Address**.</span></span> <span data-ttu-id="736fb-107">根据您设置的参数和设置方式的不同之处, 您可以将显示限制为特定容器中的特定类型的条目。</span><span class="sxs-lookup"><span data-stu-id="736fb-107">Depending on which of the many parameters you set and how you set them, you can limit your display to entries of a particular type from a particular container.</span></span>
  
 <span data-ttu-id="736fb-108">**限制 "地址" 对话框仅显示 "个人通讯簿" (PAB) 条目**</span><span class="sxs-lookup"><span data-stu-id="736fb-108">**To limit the address dialog box to displaying personal address book (PAB) entries only**</span></span>
  
1. <span data-ttu-id="736fb-109">调用[IAddrBook:: GetPAB](iaddrbook-getpab.md)以检索 PAB 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="736fb-109">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the entry identifier of the PAB.</span></span> 
    
2. <span data-ttu-id="736fb-110">创建对[SPropertyRestriction](spropertyrestriction.md)结构的**RELOP**成员使用 RELOP_EQ 的属性限制, 并使用**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 作为**ulPropTag**成员。</span><span class="sxs-lookup"><span data-stu-id="736fb-110">Create a property restriction that uses RELOP_EQ for the **relop** member of the [SPropertyRestriction](spropertyrestriction.md) structure and either **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) or **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) as the **ulPropTag** member.</span></span> <span data-ttu-id="736fb-111">如果使用**PR_ENTRYID**, 请传递从**GetPAB**中检索到的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="736fb-111">If you use **PR_ENTRYID**, pass the entry identifier retrieved from **GetPAB**.</span></span> <span data-ttu-id="736fb-112">如果使用**PR_AB_PROVIDER_ID**, 请传递 MSPAB 中包含的值。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="736fb-112">If you use **PR_AB_PROVIDER_ID**, pass the value included in the MSPAB.H header file.</span></span> <span data-ttu-id="736fb-113">**PR_AB_PROVIDER_ID**是 MAPI 设计的 PAB 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="736fb-113">**PR_AB_PROVIDER_ID** is the unique identifier for the PAB designed by MAPI.</span></span> 
    
3. <span data-ttu-id="736fb-114">使用指向属性限制的_lpHierRestriction_参数调用[IAddrBook:: Address](iaddrbook-address.md) 。</span><span class="sxs-lookup"><span data-stu-id="736fb-114">Call [IAddrBook::Address](iaddrbook-address.md) with the  _lpHierRestriction_ parameter pointing to the property restriction.</span></span> 
    

