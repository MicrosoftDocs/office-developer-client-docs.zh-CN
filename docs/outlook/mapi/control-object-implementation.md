---
title: 控制对象实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4ad62ff0-c527-4e75-a2af-b5906a7588e8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8304021565638f8a5893d0be8cd6a94ed62a8d95
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422605"
---
# <a name="control-object-implementation"></a><span data-ttu-id="d7611-103">控制对象实现</span><span class="sxs-lookup"><span data-stu-id="d7611-103">Control Object Implementation</span></span>

  
  
<span data-ttu-id="d7611-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d7611-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d7611-105">控制对象或支持[IMAPIControl: IUnknown](imapicontroliunknown.md)接口的对象由提供程序实现, 以向出现在 MAPI 对话框中的按钮添加功能。</span><span class="sxs-lookup"><span data-stu-id="d7611-105">Control objects, or objects that support the [IMAPIControl : IUnknown](imapicontroliunknown.md) interface, are implemented by providers to add functionality to a button that appears on a MAPI dialog box.</span></span> <span data-ttu-id="d7611-106">只能对按钮实现控制对象。</span><span class="sxs-lookup"><span data-stu-id="d7611-106">Control objects can only be implemented for buttons.</span></span> 
  
 <span data-ttu-id="d7611-107">**IMAPIControl**具有三种方法: [GetLastError](imapicontrol-getlasterror.md)、 [GetState](imapicontrol-getstate.md)和[Activate](imapicontrol-activate.md)。</span><span class="sxs-lookup"><span data-stu-id="d7611-107">**IMAPIControl** has three methods: [GetLastError](imapicontrol-getlasterror.md), [GetState](imapicontrol-getstate.md), and [Activate](imapicontrol-activate.md).</span></span> 
  
<span data-ttu-id="d7611-108">MAPI 调用**GetState**以确定是否禁用该按钮。</span><span class="sxs-lookup"><span data-stu-id="d7611-108">MAPI calls **GetState** to determine whether or not to disable the button.</span></span> <span data-ttu-id="d7611-109">在下列情况下, 将调用**GetState** :</span><span class="sxs-lookup"><span data-stu-id="d7611-109">**GetState** is called in the following situations:</span></span> 
  
- <span data-ttu-id="d7611-110">第一次显示按钮出现的对话框时。</span><span class="sxs-lookup"><span data-stu-id="d7611-110">When the dialog box on which the button appears is first displayed.</span></span>
    
- <span data-ttu-id="d7611-111">为按钮发出显示表通知时。</span><span class="sxs-lookup"><span data-stu-id="d7611-111">When a display table notification is issued for the button.</span></span> 
    
<span data-ttu-id="d7611-112">将_lpulState_参数的内容设置为 MAPI_DISABLED 如果用户无法与按钮和 MAPI_ENABLED 交互 (如果用户可以交互)。</span><span class="sxs-lookup"><span data-stu-id="d7611-112">Set the contents of the  _lpulState_ parameter to MAPI_DISABLED if the user cannot interact with the button and MAPI_ENABLED if the user can interact.</span></span> 
  
<span data-ttu-id="d7611-113">当用户单击此按钮时, MAPI 调用将**激活**。</span><span class="sxs-lookup"><span data-stu-id="d7611-113">When the user clicks the button, MAPI calls **Activate**.</span></span> <span data-ttu-id="d7611-114">**激活**: 执行已与按钮相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="d7611-114">**Activate** performs the task that has been associated with the button.</span></span> <span data-ttu-id="d7611-115">此任务可以是适合您的提供程序的任何内容, 如显示对话框或更新属性。</span><span class="sxs-lookup"><span data-stu-id="d7611-115">This task can be anything appropriate for your provider, such as displaying a dialog box or updating a property.</span></span> <span data-ttu-id="d7611-116">如果该任务因用户取消而失败, 则返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="d7611-116">If the task is unsuccessful because the user canceled it, return MAPI_E_USER_CANCEL.</span></span> <span data-ttu-id="d7611-117">对于失败的其他原因, 请返回相应的错误值。</span><span class="sxs-lookup"><span data-stu-id="d7611-117">For other causes of failure, return the appropriate error value.</span></span> 
  
<span data-ttu-id="d7611-118">如果任务成功, 并且它链接到的属性更改反映在对话框中的另一个控件中, 则调用[ITableData:: HrNotify](itabledata-hrnotify.md)。</span><span class="sxs-lookup"><span data-stu-id="d7611-118">If the task is successful and it is linked to a property change that is reflected in another control on the dialog box, call [ITableData::HrNotify](itabledata-hrnotify.md).</span></span> <span data-ttu-id="d7611-119">调用**HrNotify**时, 将发出显示表通知, 其中包含更改后的属性的**PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) 属性在[TABLE_NOTIFICATION](table_notification.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="d7611-119">**HrNotify** is called to issue a display table notification with the changed property's **PR_CONTROL_ID** ([PidTagControlId](pidtagcontrolid-canonical-property.md)) property in the [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> <span data-ttu-id="d7611-120">不要在结构中放置新的属性值;而是在调用[IMAPIProp:: GetProps](imapiprop-getprops.md)时返回它。</span><span class="sxs-lookup"><span data-stu-id="d7611-120">Do not place the new property value in the structure; instead, return it when [IMAPIProp::GetProps](imapiprop-getprops.md) is called.</span></span> <span data-ttu-id="d7611-121">尽管通常显示表通知不能用于禁用或启用控件, 但它可以与按钮一起使用。</span><span class="sxs-lookup"><span data-stu-id="d7611-121">Although typically a display table notification cannot be used to disable or enable a control, it can be used with a button.</span></span> <span data-ttu-id="d7611-122">MAPI 将刷新更改的控件以响应通知。</span><span class="sxs-lookup"><span data-stu-id="d7611-122">MAPI will refresh the changed control to respond to the notification.</span></span> 
  
<span data-ttu-id="d7611-123">当**激活**返回除 MAPI_E_USER_CANCEL 之外的错误时, MAPI 会调用控件的**GetLastError**方法。</span><span class="sxs-lookup"><span data-stu-id="d7611-123">MAPI calls the control's **GetLastError** method when **Activate** returns an error other than MAPI_E_USER_CANCEL.</span></span> <span data-ttu-id="d7611-124">如果**GetLastError**将扩展的错误信息放在[MAPIERROR](mapierror.md)结构中, 并在_lppMAPIError_参数的内容中返回, 则 MAPI 将为用户显示该信息。</span><span class="sxs-lookup"><span data-stu-id="d7611-124">If **GetLastError** places extended error information in the [MAPIERROR](mapierror.md) structure that it returns in the contents of the  _lppMAPIError_ parameter, MAPI displays it for the user.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7611-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7611-125">See also</span></span>



[<span data-ttu-id="d7611-126">MAPI 服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d7611-126">MAPI Service Providers</span></span>](mapi-service-providers.md)

