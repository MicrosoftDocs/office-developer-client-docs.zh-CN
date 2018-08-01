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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f6461a1e47437c5d0c2c422d727e2b00819629b0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775405"
---
# <a name="imapiforminfoopenformcontainer"></a><span data-ttu-id="150c7-103">IMAPIFormInfo::OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="150c7-103">IMAPIFormInfo::OpenFormContainer</span></span>

  
  
<span data-ttu-id="150c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="150c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="150c7-105">返回到安装了特定的窗体的窗体容器的指针。</span><span class="sxs-lookup"><span data-stu-id="150c7-105">Returns a pointer to the form container in which a particular form is installed.</span></span>
  
```cpp
HRESULT OpenFormContainer(
  LPMAPIFORMCONTAINER FAR * ppformcontainer
);
```

## <a name="parameters"></a><span data-ttu-id="150c7-106">参数</span><span class="sxs-lookup"><span data-stu-id="150c7-106">Parameters</span></span>

 <span data-ttu-id="150c7-107">_ppformcontainer_</span><span class="sxs-lookup"><span data-stu-id="150c7-107">_ppformcontainer_</span></span>
  
> <span data-ttu-id="150c7-108">[输出]指向返回窗体容器对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="150c7-108">[out] A pointer to a pointer to the returned form container object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="150c7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="150c7-109">Return value</span></span>

<span data-ttu-id="150c7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="150c7-110">S_OK</span></span> 
  
> <span data-ttu-id="150c7-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="150c7-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="150c7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="150c7-112">See also</span></span>



[<span data-ttu-id="150c7-113">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="150c7-113">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)

