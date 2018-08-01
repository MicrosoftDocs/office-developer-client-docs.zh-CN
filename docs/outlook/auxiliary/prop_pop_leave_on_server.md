---
title: PROP_POP_LEAVE_ON_SERVER
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 22d7c1e8-48b9-4768-b4de-9a9f32a3aabb
description: 指定的 POP 帐户的服务器上保留邮件副本。
ms.openlocfilehash: 9f986ff60a5824ece0a8bb91619323b58ec8b87a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774439"
---
# <a name="proppopleaveonserver"></a><span data-ttu-id="bcf9f-103">PROP_POP_LEAVE_ON_SERVER</span><span class="sxs-lookup"><span data-stu-id="bcf9f-103">PROP_POP_LEAVE_ON_SERVER</span></span>

<span data-ttu-id="bcf9f-104">指定的 POP 帐户的服务器上保留邮件副本。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-104">Specifies leaving a copy of a message on the server for a POP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="bcf9f-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="bcf9f-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="bcf9f-106">标识符：</span><span class="sxs-lookup"><span data-stu-id="bcf9f-106">Identifier:</span></span>  <br/> |<span data-ttu-id="bcf9f-107">0x1000</span><span class="sxs-lookup"><span data-stu-id="bcf9f-107">0x1000</span></span>  <br/> |
|<span data-ttu-id="bcf9f-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="bcf9f-108">Property type:</span></span>  <br/> |<span data-ttu-id="bcf9f-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="bcf9f-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="bcf9f-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="bcf9f-110">Property tag:</span></span>  <br/> |<span data-ttu-id="bcf9f-111">0x10000003</span><span class="sxs-lookup"><span data-stu-id="bcf9f-111">0x10000003</span></span>  <br/> |
|<span data-ttu-id="bcf9f-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="bcf9f-112">Access:</span></span>  <br/> |<span data-ttu-id="bcf9f-113">只读</span><span class="sxs-lookup"><span data-stu-id="bcf9f-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bcf9f-114">说明</span><span class="sxs-lookup"><span data-stu-id="bcf9f-114">Remarks</span></span>

<span data-ttu-id="bcf9f-115">下表列出了可能的值。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-115">The following table lists the possible values.</span></span> <span data-ttu-id="bcf9f-116">常量的详细信息，请参阅[常量 （帐户管理 API）](constants-account-management-api.md) 。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-116">See [Constants (Account management API)](constants-account-management-api.md) for more information on the constants.</span></span> 
  
|<span data-ttu-id="bcf9f-117">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="bcf9f-117">**Possible values**</span></span>|<span data-ttu-id="bcf9f-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="bcf9f-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bcf9f-119">**LEAVE_ON_SERVER**</span><span class="sxs-lookup"><span data-stu-id="bcf9f-119">**LEAVE_ON_SERVER**</span></span> <br/> |<span data-ttu-id="bcf9f-120">邮件下载到设备之后，POP 服务器上保留邮件的副本。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-120">Leaves a copy of the message on the POP server after downloading the message to a device.</span></span>  <br/> |
|<span data-ttu-id="bcf9f-121">**REMOVE_AFTER**</span><span class="sxs-lookup"><span data-stu-id="bcf9f-121">**REMOVE_AFTER**</span></span> <br/> |<span data-ttu-id="bcf9f-122">下载到设备之后，删除 POP 服务器邮件。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-122">Removes the message from the POP server after downloading it to a device.</span></span>  <br/> |
|<span data-ttu-id="bcf9f-123">**REMOVE_ON_NUKE**</span><span class="sxs-lookup"><span data-stu-id="bcf9f-123">**REMOVE_ON_NUKE**</span></span> <br/> |<span data-ttu-id="bcf9f-124">仅在用户从已删除邮件文件夹中删除邮件后，请从 POP 服务器中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-124">Removes the message from the POP server only after the user deletes the message from the Deleted Items folder.</span></span>  <br/> |
|<span data-ttu-id="bcf9f-125">**GET_REMOVE_AFTER_DAYS**( _ul_)</span><span class="sxs-lookup"><span data-stu-id="bcf9f-125">**GET_REMOVE_AFTER_DAYS**( _ul_)</span></span>  <br/> |<span data-ttu-id="bcf9f-126">获取将在其后从 POP 服务器中删除邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-126">Gets the number of days after which the message will be removed from the POP server.</span></span>  <br/> |
|<span data-ttu-id="bcf9f-127">**SET_REMOVE_AFTER_DAYS**（_天_）</span><span class="sxs-lookup"><span data-stu-id="bcf9f-127">**SET_REMOVE_AFTER_DAYS**( _days_)</span></span>  <br/> |<span data-ttu-id="bcf9f-128">设置将其后从 POP 服务器中删除邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="bcf9f-128">Sets the number of days after which the message will be removed from the POP server.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bcf9f-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf9f-129">See also</span></span>

- [<span data-ttu-id="bcf9f-130">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="bcf9f-130">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md) 
- [<span data-ttu-id="bcf9f-131">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="bcf9f-131">Constants (Account management API)</span></span>](constants-account-management-api.md)

