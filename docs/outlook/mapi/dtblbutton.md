---
title: DTBLBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLBUTTON
api_type:
- COM
ms.assetid: 6058c78b-05d4-45a3-988c-1fbf8322125e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8fa683fecd59ec813fee0c15d5b4f08084c645d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338309"
---
# <a name="dtblbutton"></a><span data-ttu-id="3e7ff-103">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="3e7ff-103">DTBLBUTTON</span></span>

  
  
<span data-ttu-id="3e7ff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e7ff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e7ff-105">包含根据显示表生成的对话框的按钮控件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-105">Contains information about a button control for a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3e7ff-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3e7ff-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e7ff-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3e7ff-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="3e7ff-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="3e7ff-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="3e7ff-109">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="3e7ff-109">SizedDtblButton</span></span>](sizeddtblbutton.md) <br/> |
   
```cpp
typedef struct _DTBLBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRControl;
} DTBLBUTTON, FAR *LPDTBLBUTTON;

```

## <a name="members"></a><span data-ttu-id="3e7ff-110">Members</span><span class="sxs-lookup"><span data-stu-id="3e7ff-110">Members</span></span>

 <span data-ttu-id="3e7ff-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="3e7ff-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="3e7ff-112">按钮上显示的字符字符串在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-112">Position in memory of the character string that is displayed on the button.</span></span>
    
 <span data-ttu-id="3e7ff-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="3e7ff-113">**ulFlags**</span></span>
  
> <span data-ttu-id="3e7ff-114">标志的位掩码, 用于指定**ulbLpszLabel**成员指向的标签的格式。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="3e7ff-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="3e7ff-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="3e7ff-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3e7ff-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="3e7ff-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-117">The label is in Unicode format.</span></span> <span data-ttu-id="3e7ff-118">如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="3e7ff-119">**ulPRControl**</span><span class="sxs-lookup"><span data-stu-id="3e7ff-119">**ulPRControl**</span></span>
  
> <span data-ttu-id="3e7ff-120">实现[IMAPIControl](imapicontroliunknown.md)接口的类型为 PT_OBJECT 的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-120">Property tag for a property of type PT_OBJECT that implements the [IMAPIControl](imapicontroliunknown.md) interface.</span></span> <span data-ttu-id="3e7ff-121">单击该按钮时, MAPI 将为显示表的[IMAPIProp](imapipropiunknown.md)实现调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来检索此属性。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-121">When the button is clicked, MAPI calls the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the display table's [IMAPIProp](imapipropiunknown.md) implementation to retrieve this property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3e7ff-122">注解</span><span class="sxs-lookup"><span data-stu-id="3e7ff-122">Remarks</span></span>

<span data-ttu-id="3e7ff-123">**DTBLBUTTON**结构描述一个按钮, 单击该控件时, 用户可以开始操作。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-123">A **DTBLBUTTON** structure describes a button a control that, when clicked, allows a user to begin an operation.</span></span> <span data-ttu-id="3e7ff-124">通常情况下, 单击按钮会导致显示模式对话框或调用编程任务。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-124">Typically, clicking a button causes a modal dialog box to be displayed or a programmatic task to be invoked.</span></span> <span data-ttu-id="3e7ff-125">服务提供程序可以通过按钮控件实现任何内容。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-125">Service providers can implement anything through a button control.</span></span> <span data-ttu-id="3e7ff-126">如果按钮应基于其他控件的值执行任务, 则这些控件必须已设置 DT_SET_IMMEDIATE 标志。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-126">If the button is supposed to perform a task based on the values of other controls, those controls must have set the DT_SET_IMMEDIATE flag.</span></span> 
  
<span data-ttu-id="3e7ff-127">**ulbLpszLabel**成员是显示在按钮上的字符字符串在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-127">The **ulbLpszLabel** member is the position in memory of the character string that is displayed on the button.</span></span> <span data-ttu-id="3e7ff-128">服务提供程序可以添加一个与号&amp;字符 (), 以指示按钮标签中的 Windows 加速器。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-128">Service providers can add an ampersand character (&amp;) to indicate a Windows accelerator in the button label.</span></span> <span data-ttu-id="3e7ff-129">按加速键与单击按钮具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-129">Pressing an accelerator key has the same effect as clicking the button.</span></span> 
  
<span data-ttu-id="3e7ff-130">**ulPRControl**成员描述了一个对象属性, 该属性在使用**IMAPIProp:: OpenProperty**方法打开时, 返回一个指向 control 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-130">The **ulPRControl** member describes an object property that, when opened with the **IMAPIProp::OpenProperty** method, returns a pointer to a control object.</span></span> <span data-ttu-id="3e7ff-131">实现支持**IMAPIControl**接口的 control 对象是一种扩展 MAPI 功能集和定义单击按钮时发生的操作或任务的方法。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-131">Implementing a control object that supports the **IMAPIControl** interface is a way to extend the MAPI feature set and define the operation or task that occurs when the button is clicked.</span></span> <span data-ttu-id="3e7ff-132">**IMAPIControl**提供了两种操作按钮的方法: [GetState](imapicontrol-getstate.md)可禁用或启用按钮并[激活](imapicontrol-activate.md)以处理按钮单击。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-132">**IMAPIControl** supplies two methods for manipulating buttons: [GetState](imapicontrol-getstate.md) to disable or enable buttons and [Activate](imapicontrol-activate.md) to handle button clicks.</span></span> 
  
<span data-ttu-id="3e7ff-133">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-133">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="3e7ff-134">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="3e7ff-134">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e7ff-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e7ff-135">See also</span></span>



[<span data-ttu-id="3e7ff-136">DTCTL</span><span class="sxs-lookup"><span data-stu-id="3e7ff-136">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="3e7ff-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3e7ff-137">MAPI Structures</span></span>](mapi-structures.md)

