---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串，其中包含 personAddresses 参数指定的用户的人员和图片详细信息的集合。
ms.openlocfilehash: 08b6eca193da59bbdc3c9d21d4dc9b6d0e0c884f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404531"
---
# <a name="isocialsession2getpeopledetails"></a><span data-ttu-id="0d62f-103">ISocialSession2::GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="0d62f-103">ISocialSession2::GetPeopleDetails</span></span>

<span data-ttu-id="0d62f-104">返回一个字符串，其中包含  _personAddresses_ 参数指定的用户的人员和图片详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="0d62f-104">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="0d62f-105">参数</span><span class="sxs-lookup"><span data-stu-id="0d62f-105">Parameters</span></span>

<span data-ttu-id="0d62f-106">_personsAddresses_</span><span class="sxs-lookup"><span data-stu-id="0d62f-106">_personsAddresses_</span></span>
  
> <span data-ttu-id="0d62f-107">[in]一个 XML 字符串，用于指定一组用户的哈希 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0d62f-107">[in] An XML string that specifies the hashed SMTP addresses of a set of users.</span></span>
    
<span data-ttu-id="0d62f-108">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="0d62f-108">_personsCollection_</span></span>
  
> <span data-ttu-id="0d62f-109">[out]包含人员集合和图片详细信息的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="0d62f-109">[out] An XML string that contains a collection of person and picture details.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0d62f-110">备注</span><span class="sxs-lookup"><span data-stu-id="0d62f-110">Remarks</span></span>

<span data-ttu-id="0d62f-111">如果 OSC (支持) 好友和非好友的按需同步或混合同步，则 OsC 中的 Outlook Social Connector 将调用 **GetPeopleDetails。**</span><span class="sxs-lookup"><span data-stu-id="0d62f-111">The Outlook Social Connector (OSC) calls **GetPeopleDetails** if the OSC provider supports on-demand or hybrid synchronization of friends and non-friends.</span></span> 
  
<span data-ttu-id="0d62f-112">_the personsAddresses_ parameter must conform to the schema definition for **hashedAddresses**， as defined in the schema for OSC provider extensibility.</span><span class="sxs-lookup"><span data-stu-id="0d62f-112">The  _personsAddresses_ parameter must conform to the schema definition for **hashedAddresses**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="0d62f-113">_peopleAddresses_ 字符串表示显示在人员窗格中的每个用户的一组哈希 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="0d62f-113">The  _personsAddresses_ string represents a set of hashed SMTP addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="0d62f-114">用户无需是 [ISocialSession：：LoggedOnUserName](isocialsession-loggedonusername.md) 属性所代表的已登录用户的好友。</span><span class="sxs-lookup"><span data-stu-id="0d62f-114">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> <span data-ttu-id="0d62f-115">哈希 SMTP 地址使用提供程序的功能 XML 中 **hashFunction** 元素指定的哈希函数 **进行** 加密。</span><span class="sxs-lookup"><span data-stu-id="0d62f-115">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="0d62f-116">OSC 使用索引元素标识 _personAddresses_ 集合中的每个 **hashedAddress。** </span><span class="sxs-lookup"><span data-stu-id="0d62f-116">The OSC identifies each **hashedAddress** in the  _personAddresses_ collection with an **index** element.</span></span> <span data-ttu-id="0d62f-117">当提供程序返回 **GetPeopleDetails** 的好友 **XML** 时，提供程序必须使用 **index** 元素标识收件人的人 XML。</span><span class="sxs-lookup"><span data-stu-id="0d62f-117">The provider must use the **index** element to identify the recipient's **person** XML when it returns **friends** XML for **GetPeopleDetails**.</span></span> <span data-ttu-id="0d62f-118">如果收件人不是社交网络上的注册用户，则提供程序不得 **返回该收件人** 的任何人 XML。</span><span class="sxs-lookup"><span data-stu-id="0d62f-118">If the recipient is not a registered user on the social network, the provider must not return any **person** XML for that recipient.</span></span> <span data-ttu-id="0d62f-119">person  **XML** 表示的每个网络用户的 index 元素对应于 _personAddresses_ 中收件人的索引元素。 </span><span class="sxs-lookup"><span data-stu-id="0d62f-119">The **index** element for each network user represented by **person** XML corresponds to the **index** element for the recipient in  _personsAddresses_.</span></span>
  
<span data-ttu-id="0d62f-120">OSC 将  _由 personsCollection_ 参数返回的信息存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="0d62f-120">The OSC stores the information returned by the  _personsCollection_ parameter in memory.</span></span> <span data-ttu-id="0d62f-121">_the personsCollection_ XML string must conform to the schema definition for **friends**， as defined in the schema for OSC provider extensibility.</span><span class="sxs-lookup"><span data-stu-id="0d62f-121">The  _personsCollection_ XML string must conform to the schema definition for **friends**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="0d62f-122">有关 OSC 如何在内存中使用和更新此信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="0d62f-122">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d62f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d62f-123">See also</span></span>

- [<span data-ttu-id="0d62f-124">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0d62f-124">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="0d62f-125">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="0d62f-125">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

