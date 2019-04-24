---
title: IMAPIFormInfoOpenFormContainer
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.OpenFormContainer
api_type:
- COM
ms.assetid: 1d6eec99-59f9-4700-9b83-7f7f8787a9f8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a76d0c554d7cf06aceeaa2925c199e45411b999d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342089"
---
# <a name="imapiforminfoopenformcontainer"></a><span data-ttu-id="ff82e-103">IMAPIFormInfo::OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="ff82e-103">IMAPIFormInfo::OpenFormContainer</span></span>

  
  
<span data-ttu-id="ff82e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff82e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff82e-105">返回一个指针, 指向在其中安装特定表单的表单容器。</span><span class="sxs-lookup"><span data-stu-id="ff82e-105">Returns a pointer to the form container in which a particular form is installed.</span></span>
  
```cpp
HRESULT OpenFormContainer(
  LPMAPIFORMCONTAINER FAR * ppformcontainer
);
```

## <a name="parameters"></a><span data-ttu-id="ff82e-106">参数</span><span class="sxs-lookup"><span data-stu-id="ff82e-106">Parameters</span></span>

 <span data-ttu-id="ff82e-107">_ppformcontainer_</span><span class="sxs-lookup"><span data-stu-id="ff82e-107">_ppformcontainer_</span></span>
  
> <span data-ttu-id="ff82e-108">排除指向指向返回的表单容器对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="ff82e-108">[out] A pointer to a pointer to the returned form container object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ff82e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ff82e-109">Return value</span></span>

<span data-ttu-id="ff82e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff82e-110">S_OK</span></span> 
  
> <span data-ttu-id="ff82e-111">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="ff82e-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff82e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff82e-112">See also</span></span>



[<span data-ttu-id="ff82e-113">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="ff82e-113">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

