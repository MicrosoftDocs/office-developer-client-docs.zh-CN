---
title: ISocialSessionGetPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2d0a2945-54d7-417f-b5c6-2647c70263cf
description: 获取基于用户 Id 参数 ISocialPerson 接口。
ms.openlocfilehash: 5769f4c41bb97f45ab722f1b3a3febe24c8a7ab2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779231"
---
# <a name="isocialsessiongetperson"></a><span data-ttu-id="65190-103">ISocialSession::GetPerson</span><span class="sxs-lookup"><span data-stu-id="65190-103">ISocialSession::GetPerson</span></span>

<span data-ttu-id="65190-104">获取基于_用户 Id_参数[ISocialPerson](isocialpersoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="65190-104">Gets an [ISocialPerson](isocialpersoniunknown.md) interface based on the  _userID_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetPerson([in] BSTR userId, [out, retval] ISocialPerson** result);
```

## <a name="parameters"></a><span data-ttu-id="65190-105">参数</span><span class="sxs-lookup"><span data-stu-id="65190-105">Parameters</span></span>

<span data-ttu-id="65190-106">_userId_</span><span class="sxs-lookup"><span data-stu-id="65190-106">_userId_</span></span>
  
> <span data-ttu-id="65190-107">[in]一个字符串，包含用户 ID 或 SMTP 地址的联系人。</span><span class="sxs-lookup"><span data-stu-id="65190-107">[in] A string that contains a user ID or SMTP address of a person.</span></span>
    
<span data-ttu-id="65190-108">_result_</span><span class="sxs-lookup"><span data-stu-id="65190-108">_result_</span></span>
  
> <span data-ttu-id="65190-109">[输出]**ISocialPerson**接口。</span><span class="sxs-lookup"><span data-stu-id="65190-109">[out] An **ISocialPerson** interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="65190-110">说明</span><span class="sxs-lookup"><span data-stu-id="65190-110">Remarks</span></span>

<span data-ttu-id="65190-111">_UserID_参数必须为该用户的 ID 或 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="65190-111">The  _userID_ parameter must be a user ID or SMTP address.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65190-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65190-112">See also</span></span>

- [<span data-ttu-id="65190-113">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="65190-113">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

