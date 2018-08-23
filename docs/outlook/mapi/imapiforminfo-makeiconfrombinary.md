---
title: IMAPIFormInfoMakeIconFromBinary
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.MakeIconFromBinary
api_type:
- COM
ms.assetid: 4daeddd7-3f0c-4178-ae8d-f74814090d40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 30f55044327eecee3ab0d8ee2509d7132ab6e8ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570126"
---
# <a name="imapiforminfomakeiconfrombinary"></a><span data-ttu-id="41199-103">IMAPIFormInfo::MakeIconFromBinary</span><span class="sxs-lookup"><span data-stu-id="41199-103">IMAPIFormInfo::MakeIconFromBinary</span></span>

  
  
<span data-ttu-id="41199-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41199-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41199-105">生成来自窗体的图标属性之一的图标。</span><span class="sxs-lookup"><span data-stu-id="41199-105">Builds an icon from one of the icon properties of a form.</span></span>
  
```cpp
HRESULT MakeIconFromBinary(
  ULONG nPropID,
  HICON FAR * phicon
);
```

## <a name="parameters"></a><span data-ttu-id="41199-106">参数</span><span class="sxs-lookup"><span data-stu-id="41199-106">Parameters</span></span>

 <span data-ttu-id="41199-107">_nPropID_</span><span class="sxs-lookup"><span data-stu-id="41199-107">_nPropID_</span></span>
  
> <span data-ttu-id="41199-108">[in]Icon 属性属性标识符。</span><span class="sxs-lookup"><span data-stu-id="41199-108">[in] A property identifier for an icon property.</span></span>
    
 <span data-ttu-id="41199-109">_phicon_</span><span class="sxs-lookup"><span data-stu-id="41199-109">_phicon_</span></span>
  
> <span data-ttu-id="41199-110">[输出]指向返回图标的指针。</span><span class="sxs-lookup"><span data-stu-id="41199-110">[out] A pointer to the returned icon.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="41199-111">返回值</span><span class="sxs-lookup"><span data-stu-id="41199-111">Return value</span></span>

<span data-ttu-id="41199-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="41199-112">S_OK</span></span> 
  
> <span data-ttu-id="41199-113">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="41199-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="41199-114">注解</span><span class="sxs-lookup"><span data-stu-id="41199-114">Remarks</span></span>

<span data-ttu-id="41199-115">客户端应用程序调用**IMAPIFormInfo::MakeIconFromBinary**方法生成来自窗体的图标属性之一的图标。</span><span class="sxs-lookup"><span data-stu-id="41199-115">Client applications call the **IMAPIFormInfo::MakeIconFromBinary** method to build an icon from one of the icon properties of a form.</span></span> <span data-ttu-id="41199-116">_NPropID_参数中**MakeIconFromBinary**所需窗体的图标属性之一属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="41199-116">In the  _nPropID_ parameter, **MakeIconFromBinary** takes the property identifier of one of the icon properties of a form.</span></span> <span data-ttu-id="41199-117">使用此属性标识符，它构建可包含图标的属性列的表视图中显示的图标。</span><span class="sxs-lookup"><span data-stu-id="41199-117">Using this property identifier, it builds an icon that can be displayed in table views that include property columns for icons.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="41199-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41199-118">See also</span></span>



[<span data-ttu-id="41199-119">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="41199-119">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

