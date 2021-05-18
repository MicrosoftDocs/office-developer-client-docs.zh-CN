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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412784"
---
# <a name="dtblbutton"></a><span data-ttu-id="0ef14-103">DTBLBUTTON</span><span class="sxs-lookup"><span data-stu-id="0ef14-103">DTBLBUTTON</span></span>

  
  
<span data-ttu-id="0ef14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ef14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ef14-105">包含有关从显示表构建的对话框的按钮控件的信息。</span><span class="sxs-lookup"><span data-stu-id="0ef14-105">Contains information about a button control for a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0ef14-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0ef14-106">Header file:</span></span>  <br/> |<span data-ttu-id="0ef14-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0ef14-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="0ef14-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="0ef14-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="0ef14-109">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="0ef14-109">SizedDtblButton</span></span>](sizeddtblbutton.md) <br/> |
   
```cpp
typedef struct _DTBLBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRControl;
} DTBLBUTTON, FAR *LPDTBLBUTTON;

```

## <a name="members"></a><span data-ttu-id="0ef14-110">Members</span><span class="sxs-lookup"><span data-stu-id="0ef14-110">Members</span></span>

 <span data-ttu-id="0ef14-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="0ef14-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="0ef14-112">在按钮上显示的字符字符串的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="0ef14-112">Position in memory of the character string that is displayed on the button.</span></span>
    
 <span data-ttu-id="0ef14-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="0ef14-113">**ulFlags**</span></span>
  
> <span data-ttu-id="0ef14-114">用于指定 **ulbLpszLabel** 成员指向的标签格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0ef14-114">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="0ef14-115">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="0ef14-115">The following flag can be set:</span></span> 
    
<span data-ttu-id="0ef14-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0ef14-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="0ef14-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="0ef14-117">The label is in Unicode format.</span></span> <span data-ttu-id="0ef14-118">如果未MAPI_UNICODE，则标签采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="0ef14-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="0ef14-119">**ulPRControl**</span><span class="sxs-lookup"><span data-stu-id="0ef14-119">**ulPRControl**</span></span>
  
> <span data-ttu-id="0ef14-120">实现 [IMAPIControl](imapicontroliunknown.md) 接口PT_OBJECT类型的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="0ef14-120">Property tag for a property of type PT_OBJECT that implements the [IMAPIControl](imapicontroliunknown.md) interface.</span></span> <span data-ttu-id="0ef14-121">单击该按钮时，MAPI 将调用显示表的[IMAPIProp 实现中的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以检索此属性。 [](imapipropiunknown.md)</span><span class="sxs-lookup"><span data-stu-id="0ef14-121">When the button is clicked, MAPI calls the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method for the display table's [IMAPIProp](imapipropiunknown.md) implementation to retrieve this property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="0ef14-122">备注</span><span class="sxs-lookup"><span data-stu-id="0ef14-122">Remarks</span></span>

<span data-ttu-id="0ef14-123">**DTBLBUTTON** 结构描述按钮控件，单击该控件时，用户可以开始操作。</span><span class="sxs-lookup"><span data-stu-id="0ef14-123">A **DTBLBUTTON** structure describes a button a control that, when clicked, allows a user to begin an operation.</span></span> <span data-ttu-id="0ef14-124">通常，单击某个按钮会导致显示模式对话框或调用编程任务。</span><span class="sxs-lookup"><span data-stu-id="0ef14-124">Typically, clicking a button causes a modal dialog box to be displayed or a programmatic task to be invoked.</span></span> <span data-ttu-id="0ef14-125">服务提供程序可以通过按钮控件实现任何内容。</span><span class="sxs-lookup"><span data-stu-id="0ef14-125">Service providers can implement anything through a button control.</span></span> <span data-ttu-id="0ef14-126">如果按钮应基于其他控件的值执行任务，则这些控件必须已设置DT_SET_IMMEDIATE标志。</span><span class="sxs-lookup"><span data-stu-id="0ef14-126">If the button is supposed to perform a task based on the values of other controls, those controls must have set the DT_SET_IMMEDIATE flag.</span></span> 
  
<span data-ttu-id="0ef14-127">**ulbLpszLabel** 成员是按钮上显示的字符字符串在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="0ef14-127">The **ulbLpszLabel** member is the position in memory of the character string that is displayed on the button.</span></span> <span data-ttu-id="0ef14-128">服务提供商可以添加与号字符 () 按钮标签Windows &amp; 加速键。</span><span class="sxs-lookup"><span data-stu-id="0ef14-128">Service providers can add an ampersand character (&amp;) to indicate a Windows accelerator in the button label.</span></span> <span data-ttu-id="0ef14-129">按加速键的效果与单击按钮的效果相同。</span><span class="sxs-lookup"><span data-stu-id="0ef14-129">Pressing an accelerator key has the same effect as clicking the button.</span></span> 
  
<span data-ttu-id="0ef14-130">**ulPRControl** 成员描述一个对象属性，当使用 **IMAPIProp：：OpenProperty** 方法打开该属性时，将返回一个指向控件对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0ef14-130">The **ulPRControl** member describes an object property that, when opened with the **IMAPIProp::OpenProperty** method, returns a pointer to a control object.</span></span> <span data-ttu-id="0ef14-131">实现支持 **IMAPIControl** 接口的控件对象是扩展 MAPI 功能集并定义单击按钮时发生的操作或任务的一种方式。</span><span class="sxs-lookup"><span data-stu-id="0ef14-131">Implementing a control object that supports the **IMAPIControl** interface is a way to extend the MAPI feature set and define the operation or task that occurs when the button is clicked.</span></span> <span data-ttu-id="0ef14-132">**IMAPIControl** 提供了两种操作按钮的方法：用于禁用或启用按钮的 [GetState](imapicontrol-getstate.md) 和 [用于](imapicontrol-activate.md) 处理按钮单击的激活。</span><span class="sxs-lookup"><span data-stu-id="0ef14-132">**IMAPIControl** supplies two methods for manipulating buttons: [GetState](imapicontrol-getstate.md) to disable or enable buttons and [Activate](imapicontrol-activate.md) to handle button clicks.</span></span> 
  
<span data-ttu-id="0ef14-133">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef14-133">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="0ef14-134">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="0ef14-134">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ef14-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef14-135">See also</span></span>



[<span data-ttu-id="0ef14-136">DTCTL</span><span class="sxs-lookup"><span data-stu-id="0ef14-136">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="0ef14-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0ef14-137">MAPI Structures</span></span>](mapi-structures.md)

