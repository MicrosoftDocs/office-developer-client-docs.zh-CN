---
title: 控制对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ad62ff0-c527-4e75-a2af-b5906a7588e8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 268ad60cf8161fb2b58370f89aae623aabd7da7c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774695"
---
# <a name="control-object-implementation"></a><span data-ttu-id="cd887-103">控制对象实现</span><span class="sxs-lookup"><span data-stu-id="cd887-103">Control Object Implementation</span></span>

  
  
<span data-ttu-id="cd887-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cd887-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cd887-105">控制或对象支持的对象， [IMAPIControl: IUnknown](imapicontroliunknown.md)接口，由提供商能够将功能添加到一个 MAPI 对话框中显示的按钮。</span><span class="sxs-lookup"><span data-stu-id="cd887-105">Control objects, or objects that support the [IMAPIControl : IUnknown](imapicontroliunknown.md) interface, are implemented by providers to add functionality to a button that appears on a MAPI dialog box.</span></span> <span data-ttu-id="cd887-106">只能为按钮实现控件对象。</span><span class="sxs-lookup"><span data-stu-id="cd887-106">Control objects can only be implemented for buttons.</span></span> 
  
 <span data-ttu-id="cd887-107">**IMAPIControl**具有三个方法： [GetLastError](imapicontrol-getlasterror.md)、 [GetState](imapicontrol-getstate.md)和[激活](imapicontrol-activate.md)。</span><span class="sxs-lookup"><span data-stu-id="cd887-107">**IMAPIControl** has three methods: [GetLastError](imapicontrol-getlasterror.md), [GetState](imapicontrol-getstate.md), and [Activate](imapicontrol-activate.md).</span></span> 
  
<span data-ttu-id="cd887-108">MAPI 调用**GetState**以确定禁用按钮。</span><span class="sxs-lookup"><span data-stu-id="cd887-108">MAPI calls **GetState** to determine whether or not to disable the button.</span></span> <span data-ttu-id="cd887-109">在下列情况下调用**GetState** :</span><span class="sxs-lookup"><span data-stu-id="cd887-109">**GetState** is called in the following situations:</span></span> 
  
- <span data-ttu-id="cd887-110">当首次显示显示按钮对话框。</span><span class="sxs-lookup"><span data-stu-id="cd887-110">When the dialog box on which the button appears is first displayed.</span></span>
    
- <span data-ttu-id="cd887-111">当显示表通知颁发的按钮。</span><span class="sxs-lookup"><span data-stu-id="cd887-111">When a display table notification is issued for the button.</span></span> 
    
<span data-ttu-id="cd887-112">设置为 MAPI_DISABLED _lpulState_参数的内容，如果用户不能与按钮和 MAPI_ENABLED 交互，如果用户可以进行交互。</span><span class="sxs-lookup"><span data-stu-id="cd887-112">Set the contents of the  _lpulState_ parameter to MAPI_DISABLED if the user cannot interact with the button and MAPI_ENABLED if the user can interact.</span></span> 
  
<span data-ttu-id="cd887-113">当用户单击按钮时，MAPI 调用**激活**。</span><span class="sxs-lookup"><span data-stu-id="cd887-113">When the user clicks the button, MAPI calls **Activate**.</span></span> <span data-ttu-id="cd887-114">**激活**执行的任务的已与按钮关联。</span><span class="sxs-lookup"><span data-stu-id="cd887-114">**Activate** performs the task that has been associated with the button.</span></span> <span data-ttu-id="cd887-115">此任务可以是任何适用于您的提供程序，如显示一个对话框，或更新属性。</span><span class="sxs-lookup"><span data-stu-id="cd887-115">This task can be anything appropriate for your provider, such as displaying a dialog box or updating a property.</span></span> <span data-ttu-id="cd887-116">如果由于用户取消其任务失败，则返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="cd887-116">If the task is unsuccessful because the user canceled it, return MAPI_E_USER_CANCEL.</span></span> <span data-ttu-id="cd887-117">有关故障其他原因，返回相应的错误值。</span><span class="sxs-lookup"><span data-stu-id="cd887-117">For other causes of failure, return the appropriate error value.</span></span> 
  
<span data-ttu-id="cd887-118">如果任务是成功，并且它链接到反映对话框上的另一个控件中的属性更改，则调用[ITableData::HrNotify](itabledata-hrnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="cd887-118">If the task is successful and it is linked to a property change that is reflected in another control on the dialog box, call [ITableData::HrNotify](itabledata-hrnotify.md).</span></span> <span data-ttu-id="cd887-119">**HrNotify**称为发出[TABLE_NOTIFICATION](table_notification.md)结构中的已更改的属性**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性包含的显示表通知。</span><span class="sxs-lookup"><span data-stu-id="cd887-119">**HrNotify** is called to issue a display table notification with the changed property's **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) property in the [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> <span data-ttu-id="cd887-120">在结构; 不放置新的属性值相反，它返回时调用[IMAPIProp::GetProps](imapiprop-getprops.md) 。</span><span class="sxs-lookup"><span data-stu-id="cd887-120">Do not place the new property value in the structure; instead, return it when [IMAPIProp::GetProps](imapiprop-getprops.md) is called.</span></span> <span data-ttu-id="cd887-121">尽管通常显示表通知不能用于禁用或启用的控件，它可与一个按钮。</span><span class="sxs-lookup"><span data-stu-id="cd887-121">Although typically a display table notification cannot be used to disable or enable a control, it can be used with a button.</span></span> <span data-ttu-id="cd887-122">MAPI 将刷新更改控件以响应通知。</span><span class="sxs-lookup"><span data-stu-id="cd887-122">MAPI will refresh the changed control to respond to the notification.</span></span> 
  
<span data-ttu-id="cd887-123">当**激活**返回之外 MAPI_E_USER_CANCEL 错误，MAPI 调用控件的**GetLastError**方法。</span><span class="sxs-lookup"><span data-stu-id="cd887-123">MAPI calls the control's **GetLastError** method when **Activate** returns an error other than MAPI_E_USER_CANCEL.</span></span> <span data-ttu-id="cd887-124">如果**GetLastError**放入它返回_lppMAPIError_参数的内容中的[MAPIERROR](mapierror.md)结构中的扩展的错误信息，MAPI 将显示该用户。</span><span class="sxs-lookup"><span data-stu-id="cd887-124">If **GetLastError** places extended error information in the [MAPIERROR](mapierror.md) structure that it returns in the contents of the  _lppMAPIError_ parameter, MAPI displays it for the user.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cd887-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd887-125">See also</span></span>



[<span data-ttu-id="cd887-126">MAPI 服务提供商</span><span class="sxs-lookup"><span data-stu-id="cd887-126">MAPI Service Providers</span></span>](mapi-service-providers.md)

