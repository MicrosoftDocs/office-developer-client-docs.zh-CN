---
title: 显示表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb17675a-35e0-4545-b394-789d343510aa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 07ad94c423c3be425dc905dc578f55ad2c467a95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774790"
---
# <a name="display-table-implementation"></a><span data-ttu-id="30ebf-103">显示表实现</span><span class="sxs-lookup"><span data-stu-id="30ebf-103">Display Table Implementation</span></span>

  
  
<span data-ttu-id="30ebf-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="30ebf-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="30ebf-105">显示表用于显示属性表、 特殊的对话框中，其中包含的专用于显示和可能编辑一个或多个属性的一个或多个选项卡式的属性页。</span><span class="sxs-lookup"><span data-stu-id="30ebf-105">A display table is used to show a property sheet, a special dialog box that is composed of one or more tabbed property pages dedicated to displaying and possibly editing one or more properties.</span></span> <span data-ttu-id="30ebf-106">关联与每个显示表是[IAttach: IMAPIProp](iattachimapiprop.md)接口实现。</span><span class="sxs-lookup"><span data-stu-id="30ebf-106">Associated with every display table is an [IAttach : IMAPIProp](iattachimapiprop.md) interface implementation.</span></span> <span data-ttu-id="30ebf-107">[IMAPIProp](imapipropiunknown.md)实现维护属性表中显示的属性数据。</span><span class="sxs-lookup"><span data-stu-id="30ebf-107">The [IMAPIProp](imapipropiunknown.md) implementation maintains the property data that is presented in the property sheet.</span></span> 
  
<span data-ttu-id="30ebf-108">显示表中的行代表属性表中的控件。</span><span class="sxs-lookup"><span data-stu-id="30ebf-108">The rows in a display table represent the controls in the property sheet.</span></span> <span data-ttu-id="30ebf-109">大多数控件都可以与维护**IMAPIProp**实现与属性关联。</span><span class="sxs-lookup"><span data-stu-id="30ebf-109">Most controls can be associated with properties maintained with the **IMAPIProp** implementation.</span></span> <span data-ttu-id="30ebf-110">当用户更改可修改的控件的值时，将更新的相应属性。</span><span class="sxs-lookup"><span data-stu-id="30ebf-110">When a user changes the value of a modifiable control, the corresponding property is updated.</span></span> 
  
<span data-ttu-id="30ebf-111">显示表中的列表示的控件，如在属性表、 类型、 关联的结构及其标识符中的位置的属性。</span><span class="sxs-lookup"><span data-stu-id="30ebf-111">The columns in a display table represent properties of the control, such as its position in the property sheet, its type, associated structure, and identifier.</span></span> <span data-ttu-id="30ebf-112">所需的显示表格列的完整列表，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="30ebf-112">For a complete list of required display table columns, see [Display Tables](display-tables.md).</span></span>
  
<span data-ttu-id="30ebf-113">MAPI 通过读取属性值从与显示表格关联的**IMAPIProp**实现或显示表直接向客户端应用程序的用户显示属性表。</span><span class="sxs-lookup"><span data-stu-id="30ebf-113">MAPI displays a property sheet to the user of a client application by reading property values from the **IMAPIProp** implementation associated with the display table or from the display table directly.</span></span> <span data-ttu-id="30ebf-114">当用户与属性表，MAPI 更改值在控件中，调用[IMAPIProp::SetProps](imapiprop-setprops.md)保存已更改的控件，如果设置控件的 DT_SET_IMMEDIATE 标志。</span><span class="sxs-lookup"><span data-stu-id="30ebf-114">As the user works with the property sheet, changing values in the controls, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to save a changed control if the control's DT_SET_IMMEDIATE flag is set.</span></span> <span data-ttu-id="30ebf-115">对于没有设置 DT_SET_IMMEDIATE 标志的控件，当用户通过单击**确定**或**立即应用**按钮消除对话框保存对属性的更改。</span><span class="sxs-lookup"><span data-stu-id="30ebf-115">For controls without the DT_SET_IMMEDIATE flag set, changes to properties are saved when the user dismisses the dialog box by clicking the **OK** or **Apply Now** button.</span></span> <span data-ttu-id="30ebf-116">单击这些按钮或**取消**按钮时，MAPI 从视图中删除的属性表。</span><span class="sxs-lookup"><span data-stu-id="30ebf-116">When either of these buttons or the **Cancel** button is clicked, MAPI removes the property sheet from view.</span></span> 
  
<span data-ttu-id="30ebf-117">MAPI 获取的访问权显示表，通过在**IMAPIProp**实现中调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，并要求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性或继承其中对 MAPI，如[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)所做的呼叫。</span><span class="sxs-lookup"><span data-stu-id="30ebf-117">MAPI gains access to your display table either by calling the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method in the **IMAPIProp** implementation and requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property or by inheriting it in a call that you have made to MAPI, such as [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md).</span></span>
  
<span data-ttu-id="30ebf-118">通讯簿提供程序时要求您显示有关消息用户或通讯组列表的详细信息时使用的第一个访问技术。</span><span class="sxs-lookup"><span data-stu-id="30ebf-118">The first access technique is used when address book providers are asked to show details about messaging users or distribution lists.</span></span> <span data-ttu-id="30ebf-119">进行以下处理：</span><span class="sxs-lookup"><span data-stu-id="30ebf-119">The following processing occurs:</span></span>
  
1. <span data-ttu-id="30ebf-120">客户端调用[IAddrBook::Details](iaddrbook-details.md)方法。</span><span class="sxs-lookup"><span data-stu-id="30ebf-120">A client calls the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
    
2. <span data-ttu-id="30ebf-121">MAPI 调用通讯簿提供程序的[IABLogon::OpenEntry](iablogon-openentry.md)方法来访问表示所选的项目的消息用户。</span><span class="sxs-lookup"><span data-stu-id="30ebf-121">MAPI calls the address book provider's [IABLogon::OpenEntry](iablogon-openentry.md) method to access the messaging user that represents the selected entry.</span></span> 
    
3. <span data-ttu-id="30ebf-122">MAPI 调用的消息的用户[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法来检索**PR_DETAILS_TABLE**属性，详细信息对话框的显示表。</span><span class="sxs-lookup"><span data-stu-id="30ebf-122">MAPI calls the messaging user's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to retrieve the **PR_DETAILS_TABLE** property, the display table for the details dialog box.</span></span> 
    
4. <span data-ttu-id="30ebf-123">MAPI 显示的对话框中，处理用户交互的信息，并在完成后用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="30ebf-123">MAPI displays the dialog box, handling the user's interaction with the information, and removes it when the user has finished.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="30ebf-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30ebf-124">See also</span></span>



[<span data-ttu-id="30ebf-125">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="30ebf-125">MAPI Service Providers</span></span>](mapi-service-providers.md)

