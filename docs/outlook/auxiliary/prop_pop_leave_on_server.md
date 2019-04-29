---
title: PROP_POP_LEAVE_ON_SERVER
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 22d7c1e8-48b9-4768-b4de-9a9f32a3aabb
description: 指定在服务器上为 POP 帐户保留一份邮件副本。
ms.openlocfilehash: e1bbddea0f10c07d630676960d1b330f6055e137
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410943"
---
# <a name="proppopleaveonserver"></a><span data-ttu-id="c1dd9-103">PROP_POP_LEAVE_ON_SERVER</span><span class="sxs-lookup"><span data-stu-id="c1dd9-103">PROP_POP_LEAVE_ON_SERVER</span></span>

<span data-ttu-id="c1dd9-104">指定在服务器上为 POP 帐户保留一份邮件副本。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-104">Specifies leaving a copy of a message on the server for a POP account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="c1dd9-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="c1dd9-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c1dd9-106">标识符:</span><span class="sxs-lookup"><span data-stu-id="c1dd9-106">Identifier:</span></span>  <br/> |<span data-ttu-id="c1dd9-107">0x1000</span><span class="sxs-lookup"><span data-stu-id="c1dd9-107">0x1000</span></span>  <br/> |
|<span data-ttu-id="c1dd9-108">属性类型</span><span class="sxs-lookup"><span data-stu-id="c1dd9-108">Property type:</span></span>  <br/> |<span data-ttu-id="c1dd9-109">PT_DWORD</span><span class="sxs-lookup"><span data-stu-id="c1dd9-109">PT_DWORD</span></span>  <br/> |
|<span data-ttu-id="c1dd9-110">属性标记：</span><span class="sxs-lookup"><span data-stu-id="c1dd9-110">Property tag:</span></span>  <br/> |<span data-ttu-id="c1dd9-111">0x10000003</span><span class="sxs-lookup"><span data-stu-id="c1dd9-111">0x10000003</span></span>  <br/> |
|<span data-ttu-id="c1dd9-112">访问权限</span><span class="sxs-lookup"><span data-stu-id="c1dd9-112">Access:</span></span>  <br/> |<span data-ttu-id="c1dd9-113">只读</span><span class="sxs-lookup"><span data-stu-id="c1dd9-113">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c1dd9-114">说明</span><span class="sxs-lookup"><span data-stu-id="c1dd9-114">Remarks</span></span>

<span data-ttu-id="c1dd9-115">下表列出了可能的值。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-115">The following table lists the possible values.</span></span> <span data-ttu-id="c1dd9-116">有关常量的详细信息, 请参阅[常量 (帐户管理 API)](constants-account-management-api.md) 。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-116">See [Constants (Account management API)](constants-account-management-api.md) for more information on the constants.</span></span> 
  
|<span data-ttu-id="c1dd9-117">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c1dd9-117">**Possible values**</span></span>|<span data-ttu-id="c1dd9-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1dd9-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c1dd9-119">**LEAVE_ON_SERVER**</span><span class="sxs-lookup"><span data-stu-id="c1dd9-119">**LEAVE_ON_SERVER**</span></span> <br/> |<span data-ttu-id="c1dd9-120">将邮件下载到设备后, 在 POP 服务器上留下一封邮件。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-120">Leaves a copy of the message on the POP server after downloading the message to a device.</span></span>  <br/> |
|<span data-ttu-id="c1dd9-121">**REMOVE_AFTER**</span><span class="sxs-lookup"><span data-stu-id="c1dd9-121">**REMOVE_AFTER**</span></span> <br/> |<span data-ttu-id="c1dd9-122">将邮件下载到设备后, 从 POP 服务器中删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-122">Removes the message from the POP server after downloading it to a device.</span></span>  <br/> |
|<span data-ttu-id="c1dd9-123">**REMOVE_ON_NUKE**</span><span class="sxs-lookup"><span data-stu-id="c1dd9-123">**REMOVE_ON_NUKE**</span></span> <br/> |<span data-ttu-id="c1dd9-124">仅在用户从 "已删除邮件" 文件夹中删除邮件之后, 才从 POP 服务器中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-124">Removes the message from the POP server only after the user deletes the message from the Deleted Items folder.</span></span>  <br/> |
|<span data-ttu-id="c1dd9-125">**GET_REMOVE_AFTER_DAYS**( _ul_)</span><span class="sxs-lookup"><span data-stu-id="c1dd9-125">**GET_REMOVE_AFTER_DAYS**( _ul_)</span></span>  <br/> |<span data-ttu-id="c1dd9-126">获取将从 POP 服务器中删除邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-126">Gets the number of days after which the message will be removed from the POP server.</span></span>  <br/> |
|<span data-ttu-id="c1dd9-127">**SET_REMOVE_AFTER_DAYS**(_天_)</span><span class="sxs-lookup"><span data-stu-id="c1dd9-127">**SET_REMOVE_AFTER_DAYS**( _days_)</span></span>  <br/> |<span data-ttu-id="c1dd9-128">设置将从 POP 服务器中删除邮件的天数。</span><span class="sxs-lookup"><span data-stu-id="c1dd9-128">Sets the number of days after which the message will be removed from the POP server.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c1dd9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1dd9-129">See also</span></span>

- [<span data-ttu-id="c1dd9-130">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="c1dd9-130">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md) 
- [<span data-ttu-id="c1dd9-131">常量 （帐户管理 API）</span><span class="sxs-lookup"><span data-stu-id="c1dd9-131">Constants (Account management API)</span></span>](constants-account-management-api.md)

