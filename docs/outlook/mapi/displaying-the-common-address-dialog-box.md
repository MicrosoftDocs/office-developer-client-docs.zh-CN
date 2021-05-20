---
title: 显示"公用地址"对话框
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
# <a name="displaying-the-common-address-dialog-box"></a><span data-ttu-id="58564-103">显示"公用地址"对话框</span><span class="sxs-lookup"><span data-stu-id="58564-103">Displaying the Common Address Dialog Box</span></span>

  
  
<span data-ttu-id="58564-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58564-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58564-105">"MAPI 公用地址"对话框可用于各种寻址任务，如构造收件人列表。</span><span class="sxs-lookup"><span data-stu-id="58564-105">The MAPI common address dialog box can be used for a variety of addressing tasks such as constructing a recipient list.</span></span> <span data-ttu-id="58564-106">若要显示此对话框，请调用 **IAddrBook：：Address**。</span><span class="sxs-lookup"><span data-stu-id="58564-106">To display this dialog box, call **IAddrBook::Address**.</span></span> <span data-ttu-id="58564-107">根据你设置的参数中的哪一个以及设置方式，你可以将你的显示限制为来自特定容器的特定类型的条目。</span><span class="sxs-lookup"><span data-stu-id="58564-107">Depending on which of the many parameters you set and how you set them, you can limit your display to entries of a particular type from a particular container.</span></span>
  
 <span data-ttu-id="58564-108">**将地址对话框限制为仅显示 PAB 个人通讯簿 (PAB) 条目**</span><span class="sxs-lookup"><span data-stu-id="58564-108">**To limit the address dialog box to displaying personal address book (PAB) entries only**</span></span>
  
1. <span data-ttu-id="58564-109">调用 [IAddrBook：：GetPAB](iaddrbook-getpab.md) 检索 PAB 的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="58564-109">Call [IAddrBook::GetPAB](iaddrbook-getpab.md) to retrieve the entry identifier of the PAB.</span></span> 
    
2. <span data-ttu-id="58564-110">创建一个属性限制，将 RELOP_EQ 用于 [SPropertyRestriction](spropertyrestriction.md)结构的重新倾斜成员，并使用 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 或 **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 作为 **ulPropTag** 成员。</span><span class="sxs-lookup"><span data-stu-id="58564-110">Create a property restriction that uses RELOP_EQ for the **relop** member of the [SPropertyRestriction](spropertyrestriction.md) structure and either **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) or **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) as the **ulPropTag** member.</span></span> <span data-ttu-id="58564-111">如果使用 PR_ENTRYID **，请** 传递从 **GetPAB** 检索到的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="58564-111">If you use **PR_ENTRYID**, pass the entry identifier retrieved from **GetPAB**.</span></span> <span data-ttu-id="58564-112">如果使用 **PR_AB_PROVIDER_ID**，请传递 MSPAB 中包含的值。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="58564-112">If you use **PR_AB_PROVIDER_ID**, pass the value included in the MSPAB.H header file.</span></span> <span data-ttu-id="58564-113">**PR_AB_PROVIDER_ID** MAPI 设计的 PAB 的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="58564-113">**PR_AB_PROVIDER_ID** is the unique identifier for the PAB designed by MAPI.</span></span> 
    
3. <span data-ttu-id="58564-114">使用指向属性限制的 _lpHierRestriction_ 参数调用 [IAddrBook：：Address。](iaddrbook-address.md)</span><span class="sxs-lookup"><span data-stu-id="58564-114">Call [IAddrBook::Address](iaddrbook-address.md) with the  _lpHierRestriction_ parameter pointing to the property restriction.</span></span> 
    

