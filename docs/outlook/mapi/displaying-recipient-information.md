---
title: 显示收件人信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ffec274-ee90-44c7-ab2e-7dfb502517a6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7071c05f6f59740163f97f840c7fa48d83bea815
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774821"
---
# <a name="displaying-recipient-information"></a><span data-ttu-id="29407-103">显示收件人信息</span><span class="sxs-lookup"><span data-stu-id="29407-103">Displaying recipient information</span></span>

<span data-ttu-id="29407-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="29407-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="29407-105">MAPI 提供了用于显示收件人的详细信息的常见的对话框。</span><span class="sxs-lookup"><span data-stu-id="29407-105">MAPI provides a common dialog box for showing recipient details.</span></span> <span data-ttu-id="29407-106">显示表和**IMAPIProp**实现被创建详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="29407-106">The details dialog box is created from a display table and an **IMAPIProp** implementation.</span></span> <span data-ttu-id="29407-107">显示表描述了显示的详细信息的外观和**IMAPIProp**实现收件人控件数据。</span><span class="sxs-lookup"><span data-stu-id="29407-107">The display table describes the appearance of the details display and the **IMAPIProp** implementation controls the data for the recipient.</span></span> <span data-ttu-id="29407-108">您的提供程序负责提供显示表和**IMAPIProp**实现的每个收件人。</span><span class="sxs-lookup"><span data-stu-id="29407-108">Your provider is responsible for supplying the display table and the **IMAPIProp** implementation for each recipient.</span></span> 
  
<span data-ttu-id="29407-109">创建显示表的最简单方法是定义[DTPAGE](dtpage.md)结构，并调用[BuildDisplayTable](builddisplaytable.md)。</span><span class="sxs-lookup"><span data-stu-id="29407-109">The easiest way to create the display table is to define a [DTPAGE](dtpage.md) structure and call [BuildDisplayTable](builddisplaytable.md).</span></span> <span data-ttu-id="29407-110">但是，某些提供程序，特别是只读的提供程序允许一次性收件人，创建使用**IPropData**。</span><span class="sxs-lookup"><span data-stu-id="29407-110">However, some providers, specifically read-only providers that allow the creation of one-off recipients, use **IPropData**.</span></span> <span data-ttu-id="29407-111">**IMAPIProp**实现可以是任何类型的属性对象。</span><span class="sxs-lookup"><span data-stu-id="29407-111">The **IMAPIProp** implementation can be any type of property object.</span></span> 
  
<span data-ttu-id="29407-112">有两种方法来调用此对话框： [IAddrBook::Details](iaddrbook-details.md)和[IMAPISupport::Details](imapisupport-details.md)。</span><span class="sxs-lookup"><span data-stu-id="29407-112">There are two methods for invoking this dialog box: [IAddrBook::Details](iaddrbook-details.md) and [IMAPISupport::Details](imapisupport-details.md).</span></span> <span data-ttu-id="29407-113">当您的提供商调用以下方法之一来收件人的请求的详细信息时，MAPI 通过调用与其容器的[IMAPIContainer::OpenEntry](imapicontainer-openentry.md)方法首先打开收件人。</span><span class="sxs-lookup"><span data-stu-id="29407-113">When your provider calls one of these methods to request details for a recipient, MAPI first opens the recipient by calling its container's [IMAPIContainer::OpenEntry](imapicontainer-openentry.md) method.</span></span> <span data-ttu-id="29407-114">接下来，它调用收件人的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="29407-114">Next it calls the recipient's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to request the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="29407-115">**PR_DETAILS_TABLE**是代表收件人的详细信息显示表格的属性。</span><span class="sxs-lookup"><span data-stu-id="29407-115">**PR_DETAILS_TABLE** is the property that represents a recipient's details display table.</span></span> 
  
<span data-ttu-id="29407-116">[IPropData: IMAPIProp](ipropdataimapiprop.md)接口可用于监视显示表控件上的更改，如下面的过程中所述。</span><span class="sxs-lookup"><span data-stu-id="29407-116">The [IPropData : IMAPIProp](ipropdataimapiprop.md) interface can be used to monitor changes on display table controls as described in the following procedure.</span></span> 
  
## <a name="monitor-changes-to-a-control"></a><span data-ttu-id="29407-117">监视器更改为控件</span><span class="sxs-lookup"><span data-stu-id="29407-117">Monitor changes to a control</span></span>
  
1. <span data-ttu-id="29407-118">用户获得访问控件之前，请调用[IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) IPROP_CLEAN 设置控件的访问。</span><span class="sxs-lookup"><span data-stu-id="29407-118">Before the user gains access to the control, call [IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) to set the control's access to IPROP_CLEAN.</span></span> 
    
2. <span data-ttu-id="29407-119">允许用户使用对话框。</span><span class="sxs-lookup"><span data-stu-id="29407-119">Allow the user to work with the dialog box.</span></span> 
    
3. <span data-ttu-id="29407-120">完成用户后，调用[IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md)检索控件的当前访问级别。</span><span class="sxs-lookup"><span data-stu-id="29407-120">When the user has finished, call [IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md) to retrieve the current access level of the control.</span></span> 
    
4. <span data-ttu-id="29407-121">如果的访问级别，IPROP_DIRTY 已修改的用户控件。</span><span class="sxs-lookup"><span data-stu-id="29407-121">If the access level is IPROP_DIRTY, the user has modified the control.</span></span> <span data-ttu-id="29407-122">您的提供商应：</span><span class="sxs-lookup"><span data-stu-id="29407-122">Your provider should:</span></span>
    
   - <span data-ttu-id="29407-123">调用[IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md)设置访问级别回 IPROP_CLEAN。</span><span class="sxs-lookup"><span data-stu-id="29407-123">Call [IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md) to set the access level back to IPROP_CLEAN.</span></span> 
    
   - <span data-ttu-id="29407-124">调用的属性数据对象[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索已更改的属性，并通过调用[IMAPIProp::SetProps](imapiprop-setprops.md)对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="29407-124">Call the property data object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the changed property and update it by calling [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span>
    
5. <span data-ttu-id="29407-125">如果的访问级别，仍 IPROP_CLEAN 尚未修改控件。</span><span class="sxs-lookup"><span data-stu-id="29407-125">If the access level is still IPROP_CLEAN, the control has not been modified.</span></span> 
    
<span data-ttu-id="29407-126">有关创建显示表的详细信息，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="29407-126">For more information about creating display tables, see [Display Tables](display-tables.md).</span></span>
  

