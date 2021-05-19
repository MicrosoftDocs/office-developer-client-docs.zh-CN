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
ms.openlocfilehash: 3913cb04f1f2f61ba6835b704f430d872756b227
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417362"
---
# <a name="imapiforminfo--imapiprop"></a><span data-ttu-id="0d3b8-103">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="0d3b8-103">IMAPIFormInfo : IMAPIProp</span></span>

  
  
<span data-ttu-id="0d3b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d3b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d3b8-105">使客户端应用程序能够访问表单定义特定的属性。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-105">Gives client applications access to properties that are particular to form definition.</span></span> <span data-ttu-id="0d3b8-106">通过将表单信息保留到单独的对象中，表单库提供程序无需激活表单即可向客户端描述表单。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-106">By keeping form information in a separate object, the form library provider can describe a form to a client without activating the form.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0d3b8-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-107">Header file:</span></span>  <br/> |<span data-ttu-id="0d3b8-108">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="0d3b8-108">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="0d3b8-109">公开者：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="0d3b8-110">表单信息对象</span><span class="sxs-lookup"><span data-stu-id="0d3b8-110">Form information objects</span></span>  <br/> |
|<span data-ttu-id="0d3b8-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="0d3b8-112">表单库提供程序</span><span class="sxs-lookup"><span data-stu-id="0d3b8-112">Form library providers</span></span>  <br/> |
|<span data-ttu-id="0d3b8-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-113">Called by:</span></span>  <br/> |<span data-ttu-id="0d3b8-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="0d3b8-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="0d3b8-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0d3b8-116">IID_IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="0d3b8-116">IID_IMAPIFormInfo</span></span>  <br/> |
|<span data-ttu-id="0d3b8-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="0d3b8-118">LPMAPIFORMINFO</span><span class="sxs-lookup"><span data-stu-id="0d3b8-118">LPMAPIFORMINFO</span></span>  <br/> |
|<span data-ttu-id="0d3b8-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="0d3b8-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="0d3b8-120">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="0d3b8-120">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0d3b8-121">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="0d3b8-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0d3b8-122">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="0d3b8-122">CalcFormPropSet</span></span>](imapiforminfo-calcformpropset.md) <br/> |<span data-ttu-id="0d3b8-123">返回一个指针，该指针指向窗体使用的完整属性集。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-123">Returns a pointer to the complete set of properties that a form uses.</span></span>  <br/> |
|[<span data-ttu-id="0d3b8-124">CalcVerbSet</span><span class="sxs-lookup"><span data-stu-id="0d3b8-124">CalcVerbSet</span></span>](imapiforminfo-calcverbset.md) <br/> |<span data-ttu-id="0d3b8-125">返回一个指针，该指针指向窗体使用的完整动作集。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-125">Returns a pointer to the complete set of verbs that a form uses.</span></span>  <br/> |
|[<span data-ttu-id="0d3b8-126">MakeIconFromBinary</span><span class="sxs-lookup"><span data-stu-id="0d3b8-126">MakeIconFromBinary</span></span>](imapiforminfo-makeiconfrombinary.md) <br/> |<span data-ttu-id="0d3b8-127">根据窗体的图标属性生成图标。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-127">Builds an icon from an icon property of a form.</span></span>  <br/> |
|[<span data-ttu-id="0d3b8-128">SaveForm</span><span class="sxs-lookup"><span data-stu-id="0d3b8-128">SaveForm</span></span>](imapiforminfo-saveform.md) <br/> |<span data-ttu-id="0d3b8-129">将特定表单的说明保存在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-129">Saves a description of a particular form in a configuration file.</span></span>  <br/> |
|[<span data-ttu-id="0d3b8-130">OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="0d3b8-130">OpenFormContainer</span></span>](imapiforminfo-openformcontainer.md) <br/> |<span data-ttu-id="0d3b8-131">返回一个指针，该指针指向安装了特定表单的表单容器。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-131">Returns a pointer to the form container in which a particular form is installed.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0d3b8-132">备注</span><span class="sxs-lookup"><span data-stu-id="0d3b8-132">Remarks</span></span>

<span data-ttu-id="0d3b8-133">与 MapiForm.h 头文件中定义的大多数接口不同 **，IMAPIFormInfo** 继承自 [IMAPIProp](imapipropiunknown.md) 接口，因为它通过调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法导出大多数表单信息。</span><span class="sxs-lookup"><span data-stu-id="0d3b8-133">Unlike most interfaces defined in the MapiForm.h header file, **IMAPIFormInfo** inherits from the [IMAPIProp](imapipropiunknown.md) interface, because it exports most form information through calls to the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0d3b8-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3b8-134">See also</span></span>



[<span data-ttu-id="0d3b8-135">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0d3b8-135">MAPI Interfaces</span></span>](mapi-interfaces.md)

