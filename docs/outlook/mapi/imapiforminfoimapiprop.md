---
title: IMAPIFormInfo IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo
api_type:
- COM
ms.assetid: a9fda518-11ba-42aa-85ef-dd2279e0319d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fa439d0a6fa59bac787f09c3f894a750948a0a3e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775410"
---
# <a name="imapiforminfo--imapiprop"></a><span data-ttu-id="7ebec-103">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="7ebec-103">IMAPIFormInfo : IMAPIProp</span></span>

  
  
<span data-ttu-id="7ebec-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7ebec-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7ebec-105">提供客户端应用程序访问的特定于窗体定义的属性。</span><span class="sxs-lookup"><span data-stu-id="7ebec-105">Gives client applications access to properties that are particular to form definition.</span></span> <span data-ttu-id="7ebec-106">通过将表单信息保持在独立的对象，表单库提供程序可以描述客户端的表单，而不激活窗体。</span><span class="sxs-lookup"><span data-stu-id="7ebec-106">By keeping form information in a separate object, the form library provider can describe a form to a client without activating the form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7ebec-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="7ebec-107">Header file:</span></span>  <br/> |<span data-ttu-id="7ebec-108">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="7ebec-108">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="7ebec-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="7ebec-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="7ebec-110">窗体信息对象</span><span class="sxs-lookup"><span data-stu-id="7ebec-110">Form information objects</span></span>  <br/> |
|<span data-ttu-id="7ebec-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="7ebec-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="7ebec-112">窗体库提供程序</span><span class="sxs-lookup"><span data-stu-id="7ebec-112">Form library providers</span></span>  <br/> |
|<span data-ttu-id="7ebec-113">调用：</span><span class="sxs-lookup"><span data-stu-id="7ebec-113">Called by:</span></span>  <br/> |<span data-ttu-id="7ebec-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="7ebec-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="7ebec-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="7ebec-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="7ebec-116">IID_IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="7ebec-116">IID_IMAPIFormInfo</span></span>  <br/> |
|<span data-ttu-id="7ebec-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="7ebec-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="7ebec-118">LPMAPIFORMINFO</span><span class="sxs-lookup"><span data-stu-id="7ebec-118">LPMAPIFORMINFO</span></span>  <br/> |
|<span data-ttu-id="7ebec-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="7ebec-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="7ebec-120">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="7ebec-120">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="7ebec-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="7ebec-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="7ebec-122">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="7ebec-122">CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md) <br/> |<span data-ttu-id="7ebec-123">向窗体使用的属性的完整集合中返回的指针。</span><span class="sxs-lookup"><span data-stu-id="7ebec-123">Returns a pointer to the complete set of properties that a form uses.</span></span>  <br/> |
|[<span data-ttu-id="7ebec-124">CalcVerbSet</span><span class="sxs-lookup"><span data-stu-id="7ebec-124">CalcVerbSet</span></span>](imapiforminfo-calcverbset.md) <br/> |<span data-ttu-id="7ebec-125">到谓词窗体所使用的完整集合中返回的指针。</span><span class="sxs-lookup"><span data-stu-id="7ebec-125">Returns a pointer to the complete set of verbs that a form uses.</span></span>  <br/> |
|[<span data-ttu-id="7ebec-126">MakeIconFromBinary</span><span class="sxs-lookup"><span data-stu-id="7ebec-126">MakeIconFromBinary</span></span>](imapiforminfo-makeiconfrombinary.md) <br/> |<span data-ttu-id="7ebec-127">生成来自窗体的 icon 属性的图标。</span><span class="sxs-lookup"><span data-stu-id="7ebec-127">Builds an icon from an icon property of a form.</span></span>  <br/> |
|[<span data-ttu-id="7ebec-128">SaveForm</span><span class="sxs-lookup"><span data-stu-id="7ebec-128">SaveForm</span></span>](imapiforminfo-saveform.md) <br/> |<span data-ttu-id="7ebec-129">配置文件中保存窗体特定的说明。</span><span class="sxs-lookup"><span data-stu-id="7ebec-129">Saves a description of a particular form in a configuration file.</span></span>  <br/> |
|[<span data-ttu-id="7ebec-130">OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="7ebec-130">OpenFormContainer</span></span>](imapiforminfo-openformcontainer.md) <br/> |<span data-ttu-id="7ebec-131">返回到安装了特定的窗体的窗体容器的指针。</span><span class="sxs-lookup"><span data-stu-id="7ebec-131">Returns a pointer to the form container in which a particular form is installed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7ebec-132">说明</span><span class="sxs-lookup"><span data-stu-id="7ebec-132">Remarks</span></span>

<span data-ttu-id="7ebec-133">与大多数 MapiForm.h 标头文件中定义的接口，不同**IMAPIFormInfo**从[IMAPIProp](imapipropiunknown.md)接口继承，因为它导出通过调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法的大多数表单信息。</span><span class="sxs-lookup"><span data-stu-id="7ebec-133">Unlike most interfaces defined in the MapiForm.h header file, **IMAPIFormInfo** inherits from the [IMAPIProp](imapipropiunknown.md) interface, because it exports most form information through calls to the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7ebec-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ebec-134">See also</span></span>



[<span data-ttu-id="7ebec-135">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="7ebec-135">MAPI Interfaces</span></span>](mapi-interfaces.md)

