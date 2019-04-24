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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 418056f7222d5ab05f43a3661c1811bf2ae15be8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342110"
---
# <a name="imapiforminfomakeiconfrombinary"></a><span data-ttu-id="ff727-103">IMAPIFormInfo::MakeIconFromBinary</span><span class="sxs-lookup"><span data-stu-id="ff727-103">IMAPIFormInfo::MakeIconFromBinary</span></span>

  
  
<span data-ttu-id="ff727-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff727-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff727-105">从窗体的图标属性之一生成图标。</span><span class="sxs-lookup"><span data-stu-id="ff727-105">Builds an icon from one of the icon properties of a form.</span></span>
  
```cpp
HRESULT MakeIconFromBinary(
  ULONG nPropID,
  HICON FAR * phicon
);
```

## <a name="parameters"></a><span data-ttu-id="ff727-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff727-106">Parameters</span></span>

 <span data-ttu-id="ff727-107">_nPropID_</span><span class="sxs-lookup"><span data-stu-id="ff727-107">_nPropID_</span></span>
  
> <span data-ttu-id="ff727-108">实时icon 属性的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="ff727-108">[in] A property identifier for an icon property.</span></span>
    
 <span data-ttu-id="ff727-109">_phicon_</span><span class="sxs-lookup"><span data-stu-id="ff727-109">_phicon_</span></span>
  
> <span data-ttu-id="ff727-110">排除指向返回图标的指针。</span><span class="sxs-lookup"><span data-stu-id="ff727-110">[out] A pointer to the returned icon.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ff727-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ff727-111">Return value</span></span>

<span data-ttu-id="ff727-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff727-112">S_OK</span></span> 
  
> <span data-ttu-id="ff727-113">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ff727-113">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff727-114">注解</span><span class="sxs-lookup"><span data-stu-id="ff727-114">Remarks</span></span>

<span data-ttu-id="ff727-115">客户端应用程序调用**IMAPIFormInfo:: MakeIconFromBinary**方法, 以根据窗体的图标属性之一构建图标。</span><span class="sxs-lookup"><span data-stu-id="ff727-115">Client applications call the **IMAPIFormInfo::MakeIconFromBinary** method to build an icon from one of the icon properties of a form.</span></span> <span data-ttu-id="ff727-116">在_nPropID_参数中, **MakeIconFromBinary**采用表单的图标属性之一的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="ff727-116">In the  _nPropID_ parameter, **MakeIconFromBinary** takes the property identifier of one of the icon properties of a form.</span></span> <span data-ttu-id="ff727-117">使用此属性标识符, 它将构建一个图标, 该图标可显示在包含图标属性列的表格视图中。</span><span class="sxs-lookup"><span data-stu-id="ff727-117">Using this property identifier, it builds an icon that can be displayed in table views that include property columns for icons.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ff727-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff727-118">See also</span></span>



[<span data-ttu-id="ff727-119">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ff727-119">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

