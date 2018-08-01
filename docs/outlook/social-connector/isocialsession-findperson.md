---
title: ISocialSessionFindPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a86cb847-5d49-44b8-b2bc-0e35e70395b4
description: 获取一个值，该值代表一个或多个人员 userID 参数匹配的字符串。
ms.openlocfilehash: 0b7525f853f7d97a991e2996a4e715cc53756d4a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779229"
---
# <a name="isocialsessionfindperson"></a><span data-ttu-id="ac3a4-103">ISocialSession::FindPerson</span><span class="sxs-lookup"><span data-stu-id="ac3a4-103">ISocialSession::FindPerson</span></span>

<span data-ttu-id="ac3a4-104">获取一个值，该值代表一个或多个人员_userID_参数匹配的字符串。</span><span class="sxs-lookup"><span data-stu-id="ac3a4-104">Gets a string that represents one or more persons who match the  _userID_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall FindPerson([in] BSTR userId, [out, retval] BSTR* result);
```

## <a name="parameters"></a><span data-ttu-id="ac3a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac3a4-105">Parameters</span></span>

<span data-ttu-id="ac3a4-106">_userId_</span><span class="sxs-lookup"><span data-stu-id="ac3a4-106">_userId_</span></span>
  
> <span data-ttu-id="ac3a4-107">[in]社交网络用户 ID，SMTP 地址或某个人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ac3a4-107">[in] A social network user ID, SMTP address, or display name of a person.</span></span>
    
<span data-ttu-id="ac3a4-108">_result_</span><span class="sxs-lookup"><span data-stu-id="ac3a4-108">_result_</span></span>
  
> <span data-ttu-id="ac3a4-109">[输出]一个 XML 字符串值，该值代表一个或多个人员匹配_userId_参数指定的标识信息。</span><span class="sxs-lookup"><span data-stu-id="ac3a4-109">[out] An XML string that represents one or more persons who match the identification information specified by the  _userId_ parameter.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ac3a4-110">说明</span><span class="sxs-lookup"><span data-stu-id="ac3a4-110">Remarks</span></span>

<span data-ttu-id="ac3a4-111">如果一个或多个人员匹配**FindPerson**请求，此方法将返回_结果_参数中的人员的信息。</span><span class="sxs-lookup"><span data-stu-id="ac3a4-111">If one or more persons match the **FindPerson** request, this method returns the information for those persons in the  _result_ parameter.</span></span> <span data-ttu-id="ac3a4-112">Outlook Social Connector (OSC) 提供程序扩展性的架构中定义，_结果_XML 字符串必须符合**朋友**架构定义。</span><span class="sxs-lookup"><span data-stu-id="ac3a4-112">The  _result_ XML string must comply with the schema definition for **friends**, as defined in the schema for Outlook Social Connector (OSC) provider extensibility.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ac3a4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac3a4-113">See also</span></span>

- [<span data-ttu-id="ac3a4-114">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ac3a4-114">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

