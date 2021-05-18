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
ms.openlocfilehash: 1c1a66f61fe1533e436f4e35a542f53d938b4d01
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413379"
---
# <a name="imapisession--iunknown"></a><span data-ttu-id="a5bc6-103">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5bc6-103">IMAPISession : IUnknown</span></span>

  
  
<span data-ttu-id="a5bc6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5bc6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5bc6-105">管理与 MAPI 登录会话关联的对象。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-105">Manages objects associated with a MAPI logon session.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a5bc6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-106">Header file:</span></span>  <br/> |<span data-ttu-id="a5bc6-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="a5bc6-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="a5bc6-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="a5bc6-109">会话对象</span><span class="sxs-lookup"><span data-stu-id="a5bc6-109">Session objects</span></span>  <br/> |
|<span data-ttu-id="a5bc6-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="a5bc6-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="a5bc6-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="a5bc6-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-112">Called by:</span></span>  <br/> |<span data-ttu-id="a5bc6-113">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="a5bc6-113">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="a5bc6-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="a5bc6-115">IID_IMAPISession</span><span class="sxs-lookup"><span data-stu-id="a5bc6-115">IID_IMAPISession</span></span>  <br/> |
|<span data-ttu-id="a5bc6-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="a5bc6-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="a5bc6-117">LPMAPISESSION</span><span class="sxs-lookup"><span data-stu-id="a5bc6-117">LPMAPISESSION</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="a5bc6-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="a5bc6-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="a5bc6-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="a5bc6-119">GetLastError</span></span>](imapisession-getlasterror.md) <br/> |<span data-ttu-id="a5bc6-120">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关上一个会话错误的信息。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous session error.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-121">GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="a5bc6-121">GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md) <br/> |<span data-ttu-id="a5bc6-122">提供对包含有关会话配置文件中所有邮件存储的信息的邮件存储表的访问。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-122">Provides access to the message store table that contains information about all the message stores in the session profile.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-123">OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="a5bc6-123">OpenMsgStore</span></span>](imapisession-openmsgstore.md) <br/> |<span data-ttu-id="a5bc6-124">打开邮件存储并返回 [IMsgStore](imsgstoreimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-124">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-125">OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="a5bc6-125">OpenAddressBook</span></span>](imapisession-openaddressbook.md) <br/> |<span data-ttu-id="a5bc6-126">打开 MAPI 集成通讯簿，返回 [IAddrBook](iaddrbookimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-126">Opens the MAPI integrated address book, returning an [IAddrBook](iaddrbookimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-127">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="a5bc6-127">OpenProfileSection</span></span>](imapisession-openprofilesection.md) <br/> |<span data-ttu-id="a5bc6-128">打开当前配置文件的一部分并返回 [IProfSect](iprofsectimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-128">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-129">GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="a5bc6-129">GetStatusTable</span></span>](imapisession-getstatustable.md) <br/> |<span data-ttu-id="a5bc6-130">提供对状态表（包含有关会话中所有 MAPI 资源的信息的表）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-130">Provides access to the status table, a table that contains information about all the MAPI resources in the session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-131">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="a5bc6-131">OpenEntry</span></span>](imapisession-openentry.md) <br/> |<span data-ttu-id="a5bc6-132">打开对象并返回接口指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-132">Opens an object and returns an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-133">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="a5bc6-133">CompareEntryIDs</span></span>](imapisession-compareentryids.md) <br/> |<span data-ttu-id="a5bc6-134">比较两个条目标识符以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-134">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-135">建议</span><span class="sxs-lookup"><span data-stu-id="a5bc6-135">Advise</span></span>](imapisession-advise.md) <br/> |<span data-ttu-id="a5bc6-136">注册以接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-136">Registers to receive notification of specified events that affect the session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-137">非企业</span><span class="sxs-lookup"><span data-stu-id="a5bc6-137">Unadvise</span></span>](imapisession-unadvise.md) <br/> |<span data-ttu-id="a5bc6-138">取消发送以前通过调用 **Advise** 方法设置的通知。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-138">Cancels the sending of notifications previously set up with a call to the **Advise** method.</span></span>  <br/> |
|<span data-ttu-id="a5bc6-139">**MessageOptions**</span><span class="sxs-lookup"><span data-stu-id="a5bc6-139">**MessageOptions**</span></span> <br/> | <span data-ttu-id="a5bc6-140">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="a5bc6-140">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="a5bc6-141">**QueryDefaultMessageOpt**</span><span class="sxs-lookup"><span data-stu-id="a5bc6-141">**QueryDefaultMessageOpt**</span></span> <br/> | <span data-ttu-id="a5bc6-142">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="a5bc6-142">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-143">EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="a5bc6-143">EnumAdrTypes</span></span>](imapisession-enumadrtypes.md) <br/> |<span data-ttu-id="a5bc6-144">已弃用。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-144">Deprecated.</span></span> <span data-ttu-id="a5bc6-145">返回会话中所有传输提供程序可以处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-145">Returns the address types that can be handled by all of the transport providers in the session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-146">QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="a5bc6-146">QueryIdentity</span></span>](imapisession-queryidentity.md) <br/> |<span data-ttu-id="a5bc6-147">返回提供会话的主标识的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-147">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-148">注销</span><span class="sxs-lookup"><span data-stu-id="a5bc6-148">Logoff</span></span>](imapisession-logoff.md) <br/> |<span data-ttu-id="a5bc6-149">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-149">Ends a MAPI session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-150">SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="a5bc6-150">SetDefaultStore</span></span>](imapisession-setdefaultstore.md) <br/> |<span data-ttu-id="a5bc6-151">将邮件存储建立为会话的默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-151">Establishes a message store as the default message store for the session.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-152">AdminServices</span><span class="sxs-lookup"><span data-stu-id="a5bc6-152">AdminServices</span></span>](imapisession-adminservices.md) <br/> |<span data-ttu-id="a5bc6-153">返回一 [个 IMsgServiceAdmin](imsgserviceadminiunknown.md) 指针，用于对邮件服务进行更改。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-153">Returns an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer for making changes to message services.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-154">ShowForm</span><span class="sxs-lookup"><span data-stu-id="a5bc6-154">ShowForm</span></span>](imapisession-showform.md) <br/> |<span data-ttu-id="a5bc6-155">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-155">Displays a form.</span></span>  <br/> |
|[<span data-ttu-id="a5bc6-156">PrepareForm</span><span class="sxs-lookup"><span data-stu-id="a5bc6-156">PrepareForm</span></span>](imapisession-prepareform.md) <br/> |<span data-ttu-id="a5bc6-157">创建一个 **数值令牌，ShowForm** 方法使用该令牌访问邮件。</span><span class="sxs-lookup"><span data-stu-id="a5bc6-157">Creates a numeric token that the **ShowForm** method uses to access a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a5bc6-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5bc6-158">See also</span></span>



[<span data-ttu-id="a5bc6-159">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="a5bc6-159">MAPI Interfaces</span></span>](mapi-interfaces.md)

