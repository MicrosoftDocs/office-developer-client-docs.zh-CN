---
title: 显示收件人信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ffec274-ee90-44c7-ab2e-7dfb502517a6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e1c31e5edf702dd8f172f67e7055a96ae4cfff1c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337035"
---
# <a name="displaying-recipient-information"></a><span data-ttu-id="e8720-103">显示收件人信息</span><span class="sxs-lookup"><span data-stu-id="e8720-103">Displaying recipient information</span></span>

<span data-ttu-id="e8720-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8720-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8720-105">MAPI 提供了一个用于显示收件人详细信息的通用对话框。</span><span class="sxs-lookup"><span data-stu-id="e8720-105">MAPI provides a common dialog box for showing recipient details.</span></span> <span data-ttu-id="e8720-106">"详细信息" 对话框是从显示表和**IMAPIProp**实现创建的。</span><span class="sxs-lookup"><span data-stu-id="e8720-106">The details dialog box is created from a display table and an **IMAPIProp** implementation.</span></span> <span data-ttu-id="e8720-107">显示表描述了详细信息显示和**IMAPIProp**实现控制收件人的数据的外观。</span><span class="sxs-lookup"><span data-stu-id="e8720-107">The display table describes the appearance of the details display and the **IMAPIProp** implementation controls the data for the recipient.</span></span> <span data-ttu-id="e8720-108">提供程序负责为每个收件人提供显示表和**IMAPIProp**实现。</span><span class="sxs-lookup"><span data-stu-id="e8720-108">Your provider is responsible for supplying the display table and the **IMAPIProp** implementation for each recipient.</span></span> 
  
<span data-ttu-id="e8720-109">创建显示表的最简单方法是定义[DTPAGE](dtpage.md)结构并调用[BuildDisplayTable](builddisplaytable.md)。</span><span class="sxs-lookup"><span data-stu-id="e8720-109">The easiest way to create the display table is to define a [DTPAGE](dtpage.md) structure and call [BuildDisplayTable](builddisplaytable.md).</span></span> <span data-ttu-id="e8720-110">但是, 某些提供程序是只读提供程序, 允许创建一次性收件人, 请使用**IPropData**。</span><span class="sxs-lookup"><span data-stu-id="e8720-110">However, some providers, specifically read-only providers that allow the creation of one-off recipients, use **IPropData**.</span></span> <span data-ttu-id="e8720-111">**IMAPIProp**实现可以是任何类型的属性对象。</span><span class="sxs-lookup"><span data-stu-id="e8720-111">The **IMAPIProp** implementation can be any type of property object.</span></span> 
  
<span data-ttu-id="e8720-112">有两种方法可以调用此对话框: [IAddrBook::D etails](iaddrbook-details.md)和[IMAPISupport::D etails](imapisupport-details.md)。</span><span class="sxs-lookup"><span data-stu-id="e8720-112">There are two methods for invoking this dialog box: [IAddrBook::Details](iaddrbook-details.md) and [IMAPISupport::Details](imapisupport-details.md).</span></span> <span data-ttu-id="e8720-113">当提供程序调用这些方法之一来请求获取收件人的详细信息时, MAPI 首先通过调用其容器的[IMAPIContainer:: OpenEntry](imapicontainer-openentry.md)方法来打开收件人。</span><span class="sxs-lookup"><span data-stu-id="e8720-113">When your provider calls one of these methods to request details for a recipient, MAPI first opens the recipient by calling its container's [IMAPIContainer::OpenEntry](imapicontainer-openentry.md) method.</span></span> <span data-ttu-id="e8720-114">接下来, 它调用收件人的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e8720-114">Next it calls the recipient's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to request the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="e8720-115">**PR_DETAILS_TABLE**是代表收件人的详细信息显示表的属性。</span><span class="sxs-lookup"><span data-stu-id="e8720-115">**PR_DETAILS_TABLE** is the property that represents a recipient's details display table.</span></span> 
  
<span data-ttu-id="e8720-116">[IPropData: IMAPIProp](ipropdataimapiprop.md)接口可用于监视显示表控件的更改, 如下面的过程所述。</span><span class="sxs-lookup"><span data-stu-id="e8720-116">The [IPropData : IMAPIProp](ipropdataimapiprop.md) interface can be used to monitor changes on display table controls as described in the following procedure.</span></span> 
  
## <a name="monitor-changes-to-a-control"></a><span data-ttu-id="e8720-117">监视对控件的更改</span><span class="sxs-lookup"><span data-stu-id="e8720-117">Monitor changes to a control</span></span>
  
1. <span data-ttu-id="e8720-118">在用户获得对控件的访问权限之前, 请调用[IPropData:: HrSetObjAccess](ipropdata-hrsetobjaccess.md)将控件的访问权限设置为 IPROP_CLEAN。</span><span class="sxs-lookup"><span data-stu-id="e8720-118">Before the user gains access to the control, call [IPropData::HrSetObjAccess](ipropdata-hrsetobjaccess.md) to set the control's access to IPROP_CLEAN.</span></span> 
    
2. <span data-ttu-id="e8720-119">允许用户使用对话框。</span><span class="sxs-lookup"><span data-stu-id="e8720-119">Allow the user to work with the dialog box.</span></span> 
    
3. <span data-ttu-id="e8720-120">当用户完成时, 调用[IPropData:: HrGetPropAccess](ipropdata-hrgetpropaccess.md)以检索控件的当前访问级别。</span><span class="sxs-lookup"><span data-stu-id="e8720-120">When the user has finished, call [IPropData::HrGetPropAccess](ipropdata-hrgetpropaccess.md) to retrieve the current access level of the control.</span></span> 
    
4. <span data-ttu-id="e8720-121">如果访问级别为 IPROP_DIRTY, 则用户修改了控件。</span><span class="sxs-lookup"><span data-stu-id="e8720-121">If the access level is IPROP_DIRTY, the user has modified the control.</span></span> <span data-ttu-id="e8720-122">您的提供商应执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e8720-122">Your provider should:</span></span>
    
   - <span data-ttu-id="e8720-123">调用[IPropData:: HrSetPropAccess](ipropdata-hrsetpropaccess.md)以将访问级别设置回 IPROP_CLEAN。</span><span class="sxs-lookup"><span data-stu-id="e8720-123">Call [IPropData::HrSetPropAccess](ipropdata-hrsetpropaccess.md) to set the access level back to IPROP_CLEAN.</span></span> 
    
   - <span data-ttu-id="e8720-124">调用属性数据对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索已更改的属性并通过调用[IMAPIProp:: SetProps](imapiprop-setprops.md)对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="e8720-124">Call the property data object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the changed property and update it by calling [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span>
    
5. <span data-ttu-id="e8720-125">如果访问级别仍为 IPROP_CLEAN, 则该控件尚未修改。</span><span class="sxs-lookup"><span data-stu-id="e8720-125">If the access level is still IPROP_CLEAN, the control has not been modified.</span></span> 
    
<span data-ttu-id="e8720-126">有关创建显示表的详细信息, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="e8720-126">For more information about creating display tables, see [Display Tables](display-tables.md).</span></span>
  

