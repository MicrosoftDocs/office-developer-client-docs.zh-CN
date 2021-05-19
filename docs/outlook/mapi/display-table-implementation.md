---
title: 显示表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb17675a-35e0-4545-b394-789d343510aa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6990e32445083c3465693df2c1a3d40b980853c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435262"
---
# <a name="display-table-implementation"></a><span data-ttu-id="6c3ca-103">显示表实现</span><span class="sxs-lookup"><span data-stu-id="6c3ca-103">Display Table Implementation</span></span>

  
  
<span data-ttu-id="6c3ca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c3ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c3ca-105">显示表用于显示一个属性表一个特殊的对话框，该对话框由一个或多个专用于显示和可能编辑一个或多个属性的选项卡式属性页组成。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-105">A display table is used to show a property sheet, a special dialog box that is composed of one or more tabbed property pages dedicated to displaying and possibly editing one or more properties.</span></span> <span data-ttu-id="6c3ca-106">与每个显示表关联的是 [IAttach ： IMAPIProp](iattachimapiprop.md) 接口实现。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-106">Associated with every display table is an [IAttach : IMAPIProp](iattachimapiprop.md) interface implementation.</span></span> <span data-ttu-id="6c3ca-107">[IMAPIProp](imapipropiunknown.md)实现维护数据展示的属性属性表。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-107">The [IMAPIProp](imapipropiunknown.md) implementation maintains the property data that is presented in the property sheet.</span></span> 
  
<span data-ttu-id="6c3ca-108">显示表中的行表示窗体中的属性表。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-108">The rows in a display table represent the controls in the property sheet.</span></span> <span data-ttu-id="6c3ca-109">大多数控件都可以与使用 **IMAPIProp** 实现维护的属性相关联。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-109">Most controls can be associated with properties maintained with the **IMAPIProp** implementation.</span></span> <span data-ttu-id="6c3ca-110">当用户更改可修改控件的值时，将更新相应的属性。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-110">When a user changes the value of a modifiable control, the corresponding property is updated.</span></span> 
  
<span data-ttu-id="6c3ca-111">显示表中的列表示控件的属性，如控件在控件属性表、类型、关联结构和标识符。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-111">The columns in a display table represent properties of the control, such as its position in the property sheet, its type, associated structure, and identifier.</span></span> <span data-ttu-id="6c3ca-112">有关所需显示表格列的完整列表，请参阅[Display Tables。](display-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6c3ca-112">For a complete list of required display table columns, see [Display Tables](display-tables.md).</span></span>
  
<span data-ttu-id="6c3ca-113">MAPI 通过属性表与显示表关联的 **IMAPIProp** 实现或直接读取显示表中的属性值，向客户端应用程序的用户显示数据。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-113">MAPI displays a property sheet to the user of a client application by reading property values from the **IMAPIProp** implementation associated with the display table or from the display table directly.</span></span> <span data-ttu-id="6c3ca-114">在用户使用更改控件属性表时，MAPI 调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 以保存更改的控件（如果控件的 DT_SET_IMMEDIATE 标志已设置）。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-114">As the user works with the property sheet, changing values in the controls, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to save a changed control if the control's DT_SET_IMMEDIATE flag is set.</span></span> <span data-ttu-id="6c3ca-115">对于未设置DT_SET_IMMEDIATE控件，当用户通过单击"确定"或"立即应用"按钮关闭对话框时，将保存对 **属性** 的更改。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-115">For controls without the DT_SET_IMMEDIATE flag set, changes to properties are saved when the user dismisses the dialog box by clicking the **OK** or **Apply Now** button.</span></span> <span data-ttu-id="6c3ca-116">当单击其中任一按钮或"取消"按钮时，MAPI 会从属性表中删除该按钮。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-116">When either of these buttons or the **Cancel** button is clicked, MAPI removes the property sheet from view.</span></span> 
  
<span data-ttu-id="6c3ca-117">MAPI 通过调用 [IMAPIProp 实现中的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法并请求 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性，或在调用 MAPI（如 [IMAPISupport：:D oConfigPropsheet）](imapisupport-doconfigpropsheet.md)时继承它，获取对显示表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-117">MAPI gains access to your display table either by calling the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method in the **IMAPIProp** implementation and requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property or by inheriting it in a call that you have made to MAPI, such as [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md).</span></span>
  
<span data-ttu-id="6c3ca-118">当要求通讯簿提供程序显示有关邮件用户或通讯组列表的详细信息时，会使用第一种访问技术。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-118">The first access technique is used when address book providers are asked to show details about messaging users or distribution lists.</span></span> <span data-ttu-id="6c3ca-119">将发生以下处理：</span><span class="sxs-lookup"><span data-stu-id="6c3ca-119">The following processing occurs:</span></span>
  
1. <span data-ttu-id="6c3ca-120">客户端调用 [IAddrBook：:D etails](iaddrbook-details.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-120">A client calls the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
    
2. <span data-ttu-id="6c3ca-121">MAPI 调用通讯簿提供程序的 [IABLogon：：OpenEntry](iablogon-openentry.md) 方法来访问表示所选条目的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-121">MAPI calls the address book provider's [IABLogon::OpenEntry](iablogon-openentry.md) method to access the messaging user that represents the selected entry.</span></span> 
    
3. <span data-ttu-id="6c3ca-122">MAPI 调用消息用户的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法来检索 **PR_DETAILS_TABLE** 属性，即详细信息对话框的显示表。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-122">MAPI calls the messaging user's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to retrieve the **PR_DETAILS_TABLE** property, the display table for the details dialog box.</span></span> 
    
4. <span data-ttu-id="6c3ca-123">MAPI 显示对话框，处理用户与信息的交互，在用户完成后将其删除。</span><span class="sxs-lookup"><span data-stu-id="6c3ca-123">MAPI displays the dialog box, handling the user's interaction with the information, and removes it when the user has finished.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="6c3ca-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c3ca-124">See also</span></span>



[<span data-ttu-id="6c3ca-125">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6c3ca-125">MAPI Service Providers</span></span>](mapi-service-providers.md)

