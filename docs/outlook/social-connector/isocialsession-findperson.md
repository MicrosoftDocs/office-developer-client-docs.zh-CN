---
title: ISocialSessionFindPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a86cb847-5d49-44b8-b2bc-0e35e70395b4
description: 获取一个字符串，代表与 userID 参数匹配的一个或多个人员。
ms.openlocfilehash: 1aa6478126e509c8d707d6a8d11b2c8428177bbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434793"
---
# <a name="isocialsessionfindperson"></a><span data-ttu-id="c4847-103">ISocialSession::FindPerson</span><span class="sxs-lookup"><span data-stu-id="c4847-103">ISocialSession::FindPerson</span></span>

<span data-ttu-id="c4847-104">获取一个字符串，代表与 userID 参数匹配的  _一个或多个_ 人员。</span><span class="sxs-lookup"><span data-stu-id="c4847-104">Gets a string that represents one or more persons who match the  _userID_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall FindPerson([in] BSTR userId, [out, retval] BSTR* result);
```

## <a name="parameters"></a><span data-ttu-id="c4847-105">参数</span><span class="sxs-lookup"><span data-stu-id="c4847-105">Parameters</span></span>

<span data-ttu-id="c4847-106">_userId_</span><span class="sxs-lookup"><span data-stu-id="c4847-106">_userId_</span></span>
  
> <span data-ttu-id="c4847-107">[in]社交网络用户 ID、SMTP 地址或显示名称的地址。</span><span class="sxs-lookup"><span data-stu-id="c4847-107">[in] A social network user ID, SMTP address, or display name of a person.</span></span>
    
<span data-ttu-id="c4847-108">_result_</span><span class="sxs-lookup"><span data-stu-id="c4847-108">_result_</span></span>
  
> <span data-ttu-id="c4847-109">[out]一个 XML 字符串，表示与 userId 参数指定的标识信息匹配的  _一个或多个_ 人员。</span><span class="sxs-lookup"><span data-stu-id="c4847-109">[out] An XML string that represents one or more persons who match the identification information specified by the  _userId_ parameter.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c4847-110">备注</span><span class="sxs-lookup"><span data-stu-id="c4847-110">Remarks</span></span>

<span data-ttu-id="c4847-111">如果一个或多个人员与 **FindPerson** 请求匹配，此方法在 result 参数中返回  _这些人员_ 的信息。</span><span class="sxs-lookup"><span data-stu-id="c4847-111">If one or more persons match the **FindPerson** request, this method returns the information for those persons in the  _result_ parameter.</span></span> <span data-ttu-id="c4847-112">结果 XML 字符串必须符合好友的架构定义，如 Outlook Social Connector (OSC 提供程序扩展) 架构中定义。</span><span class="sxs-lookup"><span data-stu-id="c4847-112">The  _result_ XML string must comply with the schema definition for **friends**, as defined in the schema for Outlook Social Connector (OSC) provider extensibility.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c4847-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4847-113">See also</span></span>

- [<span data-ttu-id="c4847-114">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4847-114">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

