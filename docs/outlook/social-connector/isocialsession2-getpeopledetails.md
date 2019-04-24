---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串, 其中包含 personsAddresses 参数所指定用户的人员和图片详细信息的集合。
ms.openlocfilehash: 08b6eca193da59bbdc3c9d21d4dc9b6d0e0c884f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344868"
---
# <a name="isocialsession2getpeopledetails"></a><span data-ttu-id="b0a34-103">ISocialSession2::GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="b0a34-103">ISocialSession2::GetPeopleDetails</span></span>

<span data-ttu-id="b0a34-104">返回一个字符串, 其中包含_personsAddresses_参数所指定用户的人员和图片详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="b0a34-104">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="b0a34-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0a34-105">Parameters</span></span>

<span data-ttu-id="b0a34-106">_personsAddresses_</span><span class="sxs-lookup"><span data-stu-id="b0a34-106">_personsAddresses_</span></span>
  
> <span data-ttu-id="b0a34-107">实时一个 XML 字符串, 指定一组用户的哈希 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="b0a34-107">[in] An XML string that specifies the hashed SMTP addresses of a set of users.</span></span>
    
<span data-ttu-id="b0a34-108">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="b0a34-108">_personsCollection_</span></span>
  
> <span data-ttu-id="b0a34-109">排除包含人员集合和图片详细信息的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="b0a34-109">[out] An XML string that contains a collection of person and picture details.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b0a34-110">注解</span><span class="sxs-lookup"><span data-stu-id="b0a34-110">Remarks</span></span>

<span data-ttu-id="b0a34-111">如果 .osc 提供商支持朋友和非好友的按需或混合同步, Outlook Social Connector (.osc) 将呼叫**GetPeopleDetails** 。</span><span class="sxs-lookup"><span data-stu-id="b0a34-111">The Outlook Social Connector (OSC) calls **GetPeopleDetails** if the OSC provider supports on-demand or hybrid synchronization of friends and non-friends.</span></span> 
  
<span data-ttu-id="b0a34-112">_personsAddresses_参数必须符合用于 .osc 提供程序可扩展性架构中定义的**hashedAddresses**的架构定义。</span><span class="sxs-lookup"><span data-stu-id="b0a34-112">The  _personsAddresses_ parameter must conform to the schema definition for **hashedAddresses**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="b0a34-113">_personsAddresses_字符串代表 "人员" 窗格中显示的每个用户的一组哈希 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="b0a34-113">The  _personsAddresses_ string represents a set of hashed SMTP addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="b0a34-114">用户不必是[ISocialSession:: LoggedOnUserName](isocialsession-loggedonusername.md)属性所表示的已登录用户的友元。</span><span class="sxs-lookup"><span data-stu-id="b0a34-114">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> <span data-ttu-id="b0a34-115">哈希 SMTP 地址通过使用提供程序的**功能**XML 中的**hashFunction**元素指定的哈希函数进行加密。</span><span class="sxs-lookup"><span data-stu-id="b0a34-115">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="b0a34-116">.osc 使用**index**元素标识_personAddresses_集合中的每个**hashedAddress** 。</span><span class="sxs-lookup"><span data-stu-id="b0a34-116">The OSC identifies each **hashedAddress** in the  _personAddresses_ collection with an **index** element.</span></span> <span data-ttu-id="b0a34-117">提供程序在返回**GetPeopleDetails**的**好友**xml 时, 必须使用\*\*\*\* **index**元素来标识收件人的 xml。</span><span class="sxs-lookup"><span data-stu-id="b0a34-117">The provider must use the **index** element to identify the recipient's **person** XML when it returns **friends** XML for **GetPeopleDetails**.</span></span> <span data-ttu-id="b0a34-118">如果收件人不是社交网络中已注册的用户, 则提供程序不得为该收件人返回任何**人员**XML。</span><span class="sxs-lookup"><span data-stu-id="b0a34-118">If the recipient is not a registered user on the social network, the provider must not return any **person** XML for that recipient.</span></span> <span data-ttu-id="b0a34-119">**人员**XML 表示的每个网络用户的**index**元素对应于_personsAddresses_中的收件人的**index**元素。</span><span class="sxs-lookup"><span data-stu-id="b0a34-119">The **index** element for each network user represented by **person** XML corresponds to the **index** element for the recipient in  _personsAddresses_.</span></span>
  
<span data-ttu-id="b0a34-120">.osc 将_personsCollection_参数返回的信息存储在内存中。</span><span class="sxs-lookup"><span data-stu-id="b0a34-120">The OSC stores the information returned by the  _personsCollection_ parameter in memory.</span></span> <span data-ttu-id="b0a34-121">_personsCollection_ XML 字符串必须符合针对在 .osc 提供程序扩展性架构中定义的**友元**的架构定义。</span><span class="sxs-lookup"><span data-stu-id="b0a34-121">The  _personsCollection_ XML string must conform to the schema definition for **friends**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="b0a34-122">有关 .osc 如何在内存中使用和更新此信息的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="b0a34-122">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0a34-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a34-123">See also</span></span>

- [<span data-ttu-id="b0a34-124">ISocialSession2 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b0a34-124">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="b0a34-125">同步好友和活动</span><span class="sxs-lookup"><span data-stu-id="b0a34-125">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

