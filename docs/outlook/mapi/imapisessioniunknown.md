---
title: IMAPISession IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession
api_type:
- COM
ms.assetid: 5650fa2a-6e62-451c-964e-363f7bee2344
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a37d8138547c8c4e9308dbb0ebbc6750b152d795
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775584"
---
# <a name="imapisession--iunknown"></a><span data-ttu-id="86d6c-103">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="86d6c-103">IMAPISession : IUnknown</span></span>

  
  
<span data-ttu-id="86d6c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="86d6c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="86d6c-105">管理与 MAPI 登录会话关联的对象。</span><span class="sxs-lookup"><span data-stu-id="86d6c-105">Manages objects associated with a MAPI logon session.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86d6c-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="86d6c-106">Header file:</span></span>  <br/> |<span data-ttu-id="86d6c-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="86d6c-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="86d6c-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="86d6c-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="86d6c-109">会话对象</span><span class="sxs-lookup"><span data-stu-id="86d6c-109">Session objects</span></span>  <br/> |
|<span data-ttu-id="86d6c-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="86d6c-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="86d6c-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="86d6c-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="86d6c-112">调用：</span><span class="sxs-lookup"><span data-stu-id="86d6c-112">Called by:</span></span>  <br/> |<span data-ttu-id="86d6c-113">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="86d6c-113">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="86d6c-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="86d6c-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="86d6c-115">IID_IMAPISession</span><span class="sxs-lookup"><span data-stu-id="86d6c-115">IID_IMAPISession</span></span>  <br/> |
|<span data-ttu-id="86d6c-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="86d6c-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="86d6c-117">LPMAPISESSION</span><span class="sxs-lookup"><span data-stu-id="86d6c-117">LPMAPISESSION</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="86d6c-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="86d6c-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="86d6c-119">时出错</span><span class="sxs-lookup"><span data-stu-id="86d6c-119">GetLastError</span></span>](imapisession-getlasterror.md) <br/> |<span data-ttu-id="86d6c-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关以前会话错误的信息。</span><span class="sxs-lookup"><span data-stu-id="86d6c-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous session error.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-121">GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="86d6c-121">GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md) <br/> |<span data-ttu-id="86d6c-122">提供对消息存储表包含有关会话配置文件中的所有邮件存储的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="86d6c-122">Provides access to the message store table that contains information about all the message stores in the session profile.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-123">OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="86d6c-123">OpenMsgStore</span></span>](imapisession-openmsgstore.md) <br/> |<span data-ttu-id="86d6c-124">打开的消息存储并返回进一步访问[IMsgStore](imsgstoreimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="86d6c-124">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-125">OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="86d6c-125">OpenAddressBook</span></span>](imapisession-openaddressbook.md) <br/> |<span data-ttu-id="86d6c-126">打开 MAPI 集成的通讯簿中，返回进一步访问[IAddrBook](iaddrbookimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="86d6c-126">Opens the MAPI integrated address book, returning an [IAddrBook](iaddrbookimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-127">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="86d6c-127">OpenProfileSection</span></span>](imapisession-openprofilesection.md) <br/> |<span data-ttu-id="86d6c-128">打开当前配置文件的节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="86d6c-128">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-129">GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="86d6c-129">GetStatusTable</span></span>](imapisession-getstatustable.md) <br/> |<span data-ttu-id="86d6c-130">提供对状态表中，一个表，包含会话中所有 MAPI 资源的信息的访问。</span><span class="sxs-lookup"><span data-stu-id="86d6c-130">Provides access to the status table, a table that contains information about all the MAPI resources in the session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-131">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="86d6c-131">OpenEntry</span></span>](imapisession-openentry.md) <br/> |<span data-ttu-id="86d6c-132">打开一个对象并返回进一步访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="86d6c-132">Opens an object and returns an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-133">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="86d6c-133">CompareEntryIDs</span></span>](imapisession-compareentryids.md) <br/> |<span data-ttu-id="86d6c-134">比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="86d6c-134">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-135">建议</span><span class="sxs-lookup"><span data-stu-id="86d6c-135">Advise</span></span>](imapisession-advise.md) <br/> |<span data-ttu-id="86d6c-136">注册接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="86d6c-136">Registers to receive notification of specified events that affect the session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-137">取消通知</span><span class="sxs-lookup"><span data-stu-id="86d6c-137">Unadvise</span></span>](imapisession-unadvise.md) <br/> |<span data-ttu-id="86d6c-138">取消发送通知之前设置与**Advise**方法调用。</span><span class="sxs-lookup"><span data-stu-id="86d6c-138">Cancels the sending of notifications previously set up with a call to the **Advise** method.</span></span>  <br/> |
|<span data-ttu-id="86d6c-139">**消息选项**</span><span class="sxs-lookup"><span data-stu-id="86d6c-139">**MessageOptions**</span></span> <br/> | <span data-ttu-id="86d6c-140">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="86d6c-140">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="86d6c-141">**QueryDefaultMessageOpt**</span><span class="sxs-lookup"><span data-stu-id="86d6c-141">**QueryDefaultMessageOpt**</span></span> <br/> | <span data-ttu-id="86d6c-142">*不受支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="86d6c-142">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="86d6c-143">EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="86d6c-143">EnumAdrTypes</span></span>](imapisession-enumadrtypes.md) <br/> |<span data-ttu-id="86d6c-144">已弃用。</span><span class="sxs-lookup"><span data-stu-id="86d6c-144">Deprecated.</span></span> <span data-ttu-id="86d6c-145">返回会话中的所有传输提供程序可以处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="86d6c-145">Returns the address types that can be handled by all of the transport providers in the session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-146">QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="86d6c-146">QueryIdentity</span></span>](imapisession-queryidentity.md) <br/> |<span data-ttu-id="86d6c-147">返回会话中提供的主要标识的对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="86d6c-147">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-148">注销</span><span class="sxs-lookup"><span data-stu-id="86d6c-148">Logoff</span></span>](imapisession-logoff.md) <br/> |<span data-ttu-id="86d6c-149">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="86d6c-149">Ends a MAPI session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-150">SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="86d6c-150">SetDefaultStore</span></span>](imapisession-setdefaultstore.md) <br/> |<span data-ttu-id="86d6c-151">建立会话，作为默认的邮件存储的消息存储。</span><span class="sxs-lookup"><span data-stu-id="86d6c-151">Establishes a message store as the default message store for the session.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-152">AdminServices</span><span class="sxs-lookup"><span data-stu-id="86d6c-152">AdminServices</span></span>](imapisession-adminservices.md) <br/> |<span data-ttu-id="86d6c-153">返回对消息服务的更改[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="86d6c-153">Returns an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer for making changes to message services.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-154">ShowForm</span><span class="sxs-lookup"><span data-stu-id="86d6c-154">ShowForm</span></span>](imapisession-showform.md) <br/> |<span data-ttu-id="86d6c-155">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="86d6c-155">Displays a form.</span></span>  <br/> |
|[<span data-ttu-id="86d6c-156">PrepareForm</span><span class="sxs-lookup"><span data-stu-id="86d6c-156">PrepareForm</span></span>](imapisession-prepareform.md) <br/> |<span data-ttu-id="86d6c-157">创建数值令牌**ShowForm**方法用来访问的消息。</span><span class="sxs-lookup"><span data-stu-id="86d6c-157">Creates a numeric token that the **ShowForm** method uses to access a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="86d6c-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86d6c-158">See also</span></span>



[<span data-ttu-id="86d6c-159">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="86d6c-159">MAPI Interfaces</span></span>](mapi-interfaces.md)

