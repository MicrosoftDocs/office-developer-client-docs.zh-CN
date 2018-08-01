---
title: ISocialPerson IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17a2fa12-a7ef-4a95-9875-72ec6f8ceac9
description: 表示在社交网络的人员。
ms.openlocfilehash: d6fca18ac2d2074239bd8b435bcd40971de83670
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779219"
---
# <a name="isocialperson--iunknown"></a><span data-ttu-id="23153-103">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="23153-103">ISocialPerson : IUnknown</span></span>

<span data-ttu-id="23153-104">表示在社交网络的人员。</span><span class="sxs-lookup"><span data-stu-id="23153-104">Represents a person on the social network.</span></span>
  
## <a name="members"></a><span data-ttu-id="23153-105">Members</span><span class="sxs-lookup"><span data-stu-id="23153-105">Members</span></span>

<span data-ttu-id="23153-106">下表显示了**ISocialPerson**接口上可用的成员。</span><span class="sxs-lookup"><span data-stu-id="23153-106">The following table shows the members that are available on the **ISocialPerson** interface.</span></span> 
  
|<span data-ttu-id="23153-107">**名称**</span><span class="sxs-lookup"><span data-stu-id="23153-107">**Name**</span></span>|<span data-ttu-id="23153-108">**成员类型**</span><span class="sxs-lookup"><span data-stu-id="23153-108">**Member type**</span></span>|<span data-ttu-id="23153-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="23153-109">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="23153-110">GetActivities</span><span class="sxs-lookup"><span data-stu-id="23153-110">GetActivities</span></span>](isocialperson-getactivities.md) <br/> |<span data-ttu-id="23153-111">方法</span><span class="sxs-lookup"><span data-stu-id="23153-111">Method</span></span>  <br/> |<span data-ttu-id="23153-112">Outlook Social Connector 2013 以来已弃用此方法。</span><span class="sxs-lookup"><span data-stu-id="23153-112">This method has been deprecated since Outlook Social Connector 2013.</span></span>  <br/> |
|[<span data-ttu-id="23153-113">GetDetails</span><span class="sxs-lookup"><span data-stu-id="23153-113">GetDetails</span></span>](isocialperson-getdetails.md) <br/> |<span data-ttu-id="23153-114">方法</span><span class="sxs-lookup"><span data-stu-id="23153-114">Method</span></span>  <br/> |<span data-ttu-id="23153-115">获取一个字符串，表示详细信息的人员，如名字、 姓氏和一个 URL 为配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="23153-115">Gets a string that represents details for the person, such as the first name, last name, and a URL to a profile picture.</span></span>  <br/> |
|[<span data-ttu-id="23153-116">GetFriendsAndColleagues</span><span class="sxs-lookup"><span data-stu-id="23153-116">GetFriendsAndColleagues</span></span>](isocialperson-getfriendsandcolleagues.md) <br/> |<span data-ttu-id="23153-117">方法</span><span class="sxs-lookup"><span data-stu-id="23153-117">Method</span></span>  <br/> |<span data-ttu-id="23153-118">获取一个字符串，表示的人员的集合。</span><span class="sxs-lookup"><span data-stu-id="23153-118">Gets a string that represents a collection of people.</span></span>  <br/> |
|[<span data-ttu-id="23153-119">GetFriendsAndColleaguesIDs</span><span class="sxs-lookup"><span data-stu-id="23153-119">GetFriendsAndColleaguesIDs</span></span>](isocialperson-getfriendsandcolleaguesids.md) <br/> |<span data-ttu-id="23153-120">方法</span><span class="sxs-lookup"><span data-stu-id="23153-120">Method</span></span>  <br/> |<span data-ttu-id="23153-121">当前不支持此方法。</span><span class="sxs-lookup"><span data-stu-id="23153-121">This method is currently not supported.</span></span>  <br/> |
|[<span data-ttu-id="23153-122">GetPicture</span><span class="sxs-lookup"><span data-stu-id="23153-122">GetPicture</span></span>](isocialperson-getpicture.md) <br/> |<span data-ttu-id="23153-123">方法</span><span class="sxs-lookup"><span data-stu-id="23153-123">Method</span></span>  <br/> |<span data-ttu-id="23153-124">获取包含此人的图片资源的字节数组。</span><span class="sxs-lookup"><span data-stu-id="23153-124">Gets an array of bytes that contains the picture resource for the person.</span></span>  <br/> |
|[<span data-ttu-id="23153-125">GetStatus</span><span class="sxs-lookup"><span data-stu-id="23153-125">GetStatus</span></span>](isocialperson-getstatus.md) <br/> |<span data-ttu-id="23153-126">方法</span><span class="sxs-lookup"><span data-stu-id="23153-126">Method</span></span>  <br/> |<span data-ttu-id="23153-127">当前不支持此方法。</span><span class="sxs-lookup"><span data-stu-id="23153-127">This method is currently not supported.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="23153-128">说明</span><span class="sxs-lookup"><span data-stu-id="23153-128">Remarks</span></span>

<span data-ttu-id="23153-129">Outlook Social Connector (OSC) 提供程序必须实现此接口与 OSC 进行通信。</span><span class="sxs-lookup"><span data-stu-id="23153-129">An Outlook Social Connector (OSC) provider must implement this interface to communicate with the OSC.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23153-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23153-130">See also</span></span>

- [<span data-ttu-id="23153-131">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="23153-131">Outlook Social Connector Provider Interfaces</span></span>](outlook-social-connector-provider-interfaces.md)

