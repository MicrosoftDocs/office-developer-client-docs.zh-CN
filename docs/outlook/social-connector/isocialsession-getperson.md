---
title: ISocialSessionGetPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2d0a2945-54d7-417f-b5c6-2647c70263cf
description: 获取基于 userID 参数的 ISocialPerson 接口。
ms.openlocfilehash: b54e39b3712fb57d89d03787f1e5fa0ff50ff84a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439819"
---
# <a name="isocialsessiongetperson"></a><span data-ttu-id="303d8-103">ISocialSession::GetPerson</span><span class="sxs-lookup"><span data-stu-id="303d8-103">ISocialSession::GetPerson</span></span>

<span data-ttu-id="303d8-104">获取基于 _userID_ 参数的 [ISocialPerson](isocialpersoniunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="303d8-104">Gets an [ISocialPerson](isocialpersoniunknown.md) interface based on the  _userID_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetPerson([in] BSTR userId, [out, retval] ISocialPerson** result);
```

## <a name="parameters"></a><span data-ttu-id="303d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="303d8-105">Parameters</span></span>

<span data-ttu-id="303d8-106">_userId_</span><span class="sxs-lookup"><span data-stu-id="303d8-106">_userId_</span></span>
  
> <span data-ttu-id="303d8-107">[in]包含用户 ID 或用户的 SMTP 地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="303d8-107">[in] A string that contains a user ID or SMTP address of a person.</span></span>
    
<span data-ttu-id="303d8-108">_result_</span><span class="sxs-lookup"><span data-stu-id="303d8-108">_result_</span></span>
  
> <span data-ttu-id="303d8-109">[out] **ISocialPerson** 接口。</span><span class="sxs-lookup"><span data-stu-id="303d8-109">[out] An **ISocialPerson** interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="303d8-110">备注</span><span class="sxs-lookup"><span data-stu-id="303d8-110">Remarks</span></span>

<span data-ttu-id="303d8-111">_userID_ 参数必须是用户 ID 或 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="303d8-111">The  _userID_ parameter must be a user ID or SMTP address.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="303d8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="303d8-112">See also</span></span>

- [<span data-ttu-id="303d8-113">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="303d8-113">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

