---
title: ISocialSession2GetPeopleDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8733aab9-3a8e-4924-b62f-4e871d991c72
description: 返回一个字符串，包含一人和图片 personsAddresses 参数指定用户的详细信息。
ms.openlocfilehash: 756f8de3a0615420826fe725528c92351d521832
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779246"
---
# <a name="isocialsession2getpeopledetails"></a><span data-ttu-id="86c2b-103">ISocialSession2::GetPeopleDetails</span><span class="sxs-lookup"><span data-stu-id="86c2b-103">ISocialSession2::GetPeopleDetails</span></span>

<span data-ttu-id="86c2b-104">返回一个字符串，包含一人和图片_personsAddresses_参数指定用户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="86c2b-104">Returns a string that contains a collection of person and picture details for the users specified by the  _personsAddresses_ parameter.</span></span> 
  
```cpp
HRESULT _stdcall GetPeopleDetails([in] BSTR personsAddresses, [out, retval] BSTR* personsCollection);
```

## <a name="parameters"></a><span data-ttu-id="86c2b-105">参数</span><span class="sxs-lookup"><span data-stu-id="86c2b-105">Parameters</span></span>

<span data-ttu-id="86c2b-106">_personsAddresses_</span><span class="sxs-lookup"><span data-stu-id="86c2b-106">_personsAddresses_</span></span>
  
> <span data-ttu-id="86c2b-107">[in]指定一组用户的哈希的 SMTP 地址一个 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="86c2b-107">[in] An XML string that specifies the hashed SMTP addresses of a set of users.</span></span>
    
<span data-ttu-id="86c2b-108">_personsCollection_</span><span class="sxs-lookup"><span data-stu-id="86c2b-108">_personsCollection_</span></span>
  
> <span data-ttu-id="86c2b-109">[输出]一个 XML 字符串，包含人和图片的详细信息的集合。</span><span class="sxs-lookup"><span data-stu-id="86c2b-109">[out] An XML string that contains a collection of person and picture details.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="86c2b-110">备注</span><span class="sxs-lookup"><span data-stu-id="86c2b-110">Remarks</span></span>

<span data-ttu-id="86c2b-111">Outlook Social Connector (OSC) 调用**GetPeopleDetails**如果 OSC 提供程序支持的朋友和非朋友点播或混合同步。</span><span class="sxs-lookup"><span data-stu-id="86c2b-111">The Outlook Social Connector (OSC) calls **GetPeopleDetails** if the OSC provider supports on-demand or hybrid synchronization of friends and non-friends.</span></span> 
  
<span data-ttu-id="86c2b-112">OSC 提供程序扩展性的架构中定义， _personsAddresses_参数必须符合**hashedAddresses**，架构定义。</span><span class="sxs-lookup"><span data-stu-id="86c2b-112">The  _personsAddresses_ parameter must conform to the schema definition for **hashedAddresses**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="86c2b-113">_PersonsAddresses_字符串表示为人员窗格中显示每个用户的哈希 SMTP 地址的一组。</span><span class="sxs-lookup"><span data-stu-id="86c2b-113">The  _personsAddresses_ string represents a set of hashed SMTP addresses for each user displayed in the People Pane.</span></span> <span data-ttu-id="86c2b-114">用户不必是由[ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md)属性表示的登录用户的好帮手。</span><span class="sxs-lookup"><span data-stu-id="86c2b-114">The user does not have to be a friend of the logged-on user represented by the [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md) property.</span></span> <span data-ttu-id="86c2b-115">使用提供程序的**功能**XML 中指定**hashFunction**元素的哈希函数进行加密的哈希的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="86c2b-115">The hashed SMTP addresses are encrypted by using the hashing function specified by the **hashFunction** element in the provider's **capabilities** XML.</span></span> <span data-ttu-id="86c2b-116">OSC 标识与**索引**元素_personAddresses_集合中每个**hashedAddress** 。</span><span class="sxs-lookup"><span data-stu-id="86c2b-116">The OSC identifies each **hashedAddress** in the  _personAddresses_ collection with an **index** element.</span></span> <span data-ttu-id="86c2b-117">提供程序必须使用**索引**元素时它返回**朋友**XML **GetPeopleDetails**标识收件人的**人员**XML。</span><span class="sxs-lookup"><span data-stu-id="86c2b-117">The provider must use the **index** element to identify the recipient's **person** XML when it returns **friends** XML for **GetPeopleDetails**.</span></span> <span data-ttu-id="86c2b-118">如果收件人不是注册的用户社交网络上，提供的收件人必须不返回任何**人**XML。</span><span class="sxs-lookup"><span data-stu-id="86c2b-118">If the recipient is not a registered user on the social network, the provider must not return any **person** XML for that recipient.</span></span> <span data-ttu-id="86c2b-119">由**人员**XML 每个网络用户的**索引**元素中_personsAddresses_收件人对应的**索引**元素。</span><span class="sxs-lookup"><span data-stu-id="86c2b-119">The **index** element for each network user represented by **person** XML corresponds to the **index** element for the recipient in  _personsAddresses_.</span></span>
  
<span data-ttu-id="86c2b-120">OSC 存储在内存中_personsCollection_参数返回的信息。</span><span class="sxs-lookup"><span data-stu-id="86c2b-120">The OSC stores the information returned by the  _personsCollection_ parameter in memory.</span></span> <span data-ttu-id="86c2b-121">OSC 提供程序扩展性的架构中定义， _personsCollection_ XML 字符串必须符合**朋友**架构定义。</span><span class="sxs-lookup"><span data-stu-id="86c2b-121">The  _personsCollection_ XML string must conform to the schema definition for **friends**, as defined in the schema for OSC provider extensibility.</span></span> <span data-ttu-id="86c2b-122">有关如何 OSC 使用和更新内存中的此信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="86c2b-122">For more information about how the OSC uses and updates this information in memory, see [Synchronizing Friends and Activities](synchronizing-friends-and-activities.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86c2b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86c2b-123">See also</span></span>

- [<span data-ttu-id="86c2b-124">ISocialSession2: IUnknown</span><span class="sxs-lookup"><span data-stu-id="86c2b-124">ISocialSession2 : IUnknown</span></span>](isocialsession2iunknown.md)
- [<span data-ttu-id="86c2b-125">同步朋友和活动</span><span class="sxs-lookup"><span data-stu-id="86c2b-125">Synchronizing Friends and Activities</span></span>](synchronizing-friends-and-activities.md)

