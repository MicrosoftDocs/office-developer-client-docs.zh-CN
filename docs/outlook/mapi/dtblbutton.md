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
ms.openlocfilehash: e0797364eb4ec24793f64bad2f4d838507c236e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571064"
---
# <a name="dtblbutton"></a><span data-ttu-id="5d4f0-103">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="5d4f0-103">DTBLBUTTON</span></span>

  
  
<span data-ttu-id="5d4f0-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5d4f0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5d4f0-105">包含显示表中生成的对话框的按钮控件的信息。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-105">Contains information about a button control for a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5d4f0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="5d4f0-106">Header file:</span></span>  <br/> |<span data-ttu-id="5d4f0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5d4f0-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="5d4f0-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="5d4f0-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="5d4f0-109">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="5d4f0-109">SizedDtblButton</span></span>](sizeddtblbutton.md) <br/> |
   
```cpp
typedef struct _DTBLBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRControl;
} DTBLBUTTON, FAR *LPDTBLBUTTON;

```

## <a name="members"></a><span data-ttu-id="5d4f0-110">Members</span><span class="sxs-lookup"><span data-stu-id="5d4f0-110">Members</span></span>

 <span data-ttu-id="5d4f0-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="5d4f0-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="5d4f0-112">在按钮上显示的字符字符串的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-112">Position in memory of the character string that is displayed on the button.</span></span>
    
 <span data-ttu-id="5d4f0-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="5d4f0-113">**ulFlags**</span></span>
  
> <span data-ttu-id="5d4f0-114">用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="5d4f0-115">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="5d4f0-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="5d4f0-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="5d4f0-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="5d4f0-117">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-117">The label is in Unicode format.</span></span> <span data-ttu-id="5d4f0-118">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="5d4f0-119">**ulPRControl**</span><span class="sxs-lookup"><span data-stu-id="5d4f0-119">**ulPRControl**</span></span>
  
> <span data-ttu-id="5d4f0-120">属性标记 PT_OBJECT 实现[IMAPIControl](imapicontroliunknown.md)接口的类型的属性。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-120">Property tag for a property of type PT_OBJECT that implements the [IMAPIControl](imapicontroliunknown.md) interface.</span></span> <span data-ttu-id="5d4f0-121">当单击按钮时，MAPI 调用显示表[IMAPIProp](imapipropiunknown.md)实现，以检索此属性的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-121">When the button is clicked, MAPI calls the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the display table's [IMAPIProp](imapipropiunknown.md) implementation to retrieve this property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5d4f0-122">注解</span><span class="sxs-lookup"><span data-stu-id="5d4f0-122">Remarks</span></span>

<span data-ttu-id="5d4f0-123">**DTBLBUTTON**结构描述一个按钮控件，单击时，允许用户开始操作。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-123">A **DTBLBUTTON** structure describes a button a control that, when clicked, allows a user to begin an operation.</span></span> <span data-ttu-id="5d4f0-124">通常情况下，单击按钮会将显示一个模式对话框或要调用的编程任务。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-124">Typically, clicking a button causes a modal dialog box to be displayed or a programmatic task to be invoked.</span></span> <span data-ttu-id="5d4f0-125">服务提供商可以实现通过一个按钮控件的任何内容。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-125">Service providers can implement anything through a button control.</span></span> <span data-ttu-id="5d4f0-126">如果按钮应该执行任务基于其他控件的值，这些控件必须设置 DT_SET_IMMEDIATE 标志。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-126">If the button is supposed to perform a task based on the values of other controls, those controls must have set the DT_SET_IMMEDIATE flag.</span></span> 
  
<span data-ttu-id="5d4f0-127">**UlbLpszLabel**成员是在按钮上显示的字符字符串的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-127">The **ulbLpszLabel** member is the position in memory of the character string that is displayed on the button.</span></span> <span data-ttu-id="5d4f0-128">服务提供商可以添加 & 字符 (&amp;) 以指示在按钮标签 Windows 加速键。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-128">Service providers can add an ampersand character (&amp;) to indicate a Windows accelerator in the button label.</span></span> <span data-ttu-id="5d4f0-129">按加速键与单击的按钮的效果相同。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-129">Pressing an accelerator key has the same effect as clicking the button.</span></span> 
  
<span data-ttu-id="5d4f0-130">**UlPRControl**成员介绍对象属性，当用**IMAPIProp::OpenProperty**方法打开，返回指向 control 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-130">The **ulPRControl** member describes an object property that, when opened with the **IMAPIProp::OpenProperty** method, returns a pointer to a control object.</span></span> <span data-ttu-id="5d4f0-131">实现支持**IMAPIControl**接口的控件对象是一种方法扩展 MAPI 功能集，并定义操作或任务的单击按钮时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-131">Implementing a control object that supports the **IMAPIControl** interface is a way to extend the MAPI feature set and define the operation or task that occurs when the button is clicked.</span></span> <span data-ttu-id="5d4f0-132">**IMAPIControl**提供操作按钮的两种方法： [GetState](imapicontrol-getstate.md)禁用或启用按钮和[激活](imapicontrol-activate.md)处理按钮单击。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-132">**IMAPIControl** supplies two methods for manipulating buttons: [GetState](imapicontrol-getstate.md) to disable or enable buttons and [Activate](imapicontrol-activate.md) to handle button clicks.</span></span> 
  
<span data-ttu-id="5d4f0-133">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-133">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="5d4f0-134">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="5d4f0-134">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5d4f0-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d4f0-135">See also</span></span>



[<span data-ttu-id="5d4f0-136">DTCTL</span><span class="sxs-lookup"><span data-stu-id="5d4f0-136">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="5d4f0-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5d4f0-137">MAPI Structures</span></span>](mapi-structures.md)

