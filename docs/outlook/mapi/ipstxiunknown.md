---
title: IPSTX IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTX
api_type:
- COM
ms.assetid: 73752f57-6fbc-0201-bf95-0e75c56c04e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4c758ecd0134ca11ced6f771303896bd885a22c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436221"
---
# <a name="ipstx--iunknown"></a><span data-ttu-id="e4d73-103">IPSTX : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e4d73-103">IPSTX : IUnknown</span></span>

  
  
<span data-ttu-id="e4d73-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e4d73-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e4d73-105">通过 **[IOSTX](iostxiunknown.md)** 接口执行复制时，此接口提供帮助程序功能。</span><span class="sxs-lookup"><span data-stu-id="e4d73-105">This interface provides helper functionality when performing replication through the **[IOSTX](iostxiunknown.md)** interface.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e4d73-106">提供方</span><span class="sxs-lookup"><span data-stu-id="e4d73-106">Provided by</span></span>  <br/> |<span data-ttu-id="e4d73-107">对 [IMsgStore 的查询](imsgstoreimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="e4d73-107">Query on [IMsgStore](imsgstoreimapiprop.md)</span></span> <br/> |
|<span data-ttu-id="e4d73-108">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e4d73-108">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e4d73-109">IID_IPSTX</span><span class="sxs-lookup"><span data-stu-id="e4d73-109">IID_IPSTX</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e4d73-110">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="e4d73-110">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e4d73-111">**[GetLastError](ipstx-getlasterror.md)**</span><span class="sxs-lookup"><span data-stu-id="e4d73-111">**[GetLastError](ipstx-getlasterror.md)**</span></span> <br/> |<span data-ttu-id="e4d73-112">获取有关最后一个错误的扩展信息。</span><span class="sxs-lookup"><span data-stu-id="e4d73-112">Gets extended information about the last error.</span></span>  <br/> |
|<span data-ttu-id="e4d73-113">**[GetSyncObject](ipstx-getsyncobject.md)**</span><span class="sxs-lookup"><span data-stu-id="e4d73-113">**[GetSyncObject](ipstx-getsyncobject.md)**</span></span> <br/> |<span data-ttu-id="e4d73-114">获取关联的 **[IOSTX](iostxiunknown.md)** 接口。</span><span class="sxs-lookup"><span data-stu-id="e4d73-114">Gets the associated **[IOSTX](iostxiunknown.md)** interface.</span></span>  <br/> |
| <span data-ttu-id="e4d73-115">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-115">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-116">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-116">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-117">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-117">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-118">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-118">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-119">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-119">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-120">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-120">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-121">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-121">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-122">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-122">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="e4d73-123">**[EmulateSpooler](ipstx-emulatespooler.md)**</span><span class="sxs-lookup"><span data-stu-id="e4d73-123">**[EmulateSpooler](ipstx-emulatespooler.md)**</span></span> <br/> |<span data-ttu-id="e4d73-124">设置本地存储以模拟 Outlook 协议管理器，以将传出邮件后台打印到服务器。</span><span class="sxs-lookup"><span data-stu-id="e4d73-124">Sets a local store to emulate the Outlook Protocol Manager to spool outgoing messages to a server.</span></span>  <br/> |
| <span data-ttu-id="e4d73-125">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-125">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-126">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-126">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-127">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-127">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-128">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-128">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-129">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-129">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-130">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-130">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-131">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-131">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-132">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-132">*Not supported or documented.*</span></span>  <br/> |
| <span data-ttu-id="e4d73-133">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="e4d73-133">*Placeholder member*</span></span>  <br/> | <span data-ttu-id="e4d73-134">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="e4d73-134">*Not supported or documented.*</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e4d73-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4d73-135">See also</span></span>



[<span data-ttu-id="e4d73-136">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="e4d73-136">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="e4d73-137">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e4d73-137">MAPI Constants</span></span>](mapi-constants.md)

