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
# <a name="imapisession--iunknown"></a><span data-ttu-id="3e80b-103">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3e80b-103">IMAPISession : IUnknown</span></span>

  
  
<span data-ttu-id="3e80b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e80b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e80b-105">管理与 MAPI 登录会话关联的对象。</span><span class="sxs-lookup"><span data-stu-id="3e80b-105">Manages objects associated with a MAPI logon session.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3e80b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3e80b-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e80b-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="3e80b-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="3e80b-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="3e80b-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="3e80b-109">Session 对象</span><span class="sxs-lookup"><span data-stu-id="3e80b-109">Session objects</span></span>  <br/> |
|<span data-ttu-id="3e80b-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="3e80b-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="3e80b-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="3e80b-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="3e80b-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="3e80b-112">Called by:</span></span>  <br/> |<span data-ttu-id="3e80b-113">客户端应用程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="3e80b-113">Client applications and MAPI</span></span>  <br/> |
|<span data-ttu-id="3e80b-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="3e80b-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="3e80b-115">IID_IMAPISession</span><span class="sxs-lookup"><span data-stu-id="3e80b-115">IID_IMAPISession</span></span>  <br/> |
|<span data-ttu-id="3e80b-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="3e80b-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="3e80b-117">LPMAPISESSION</span><span class="sxs-lookup"><span data-stu-id="3e80b-117">LPMAPISESSION</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="3e80b-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="3e80b-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="3e80b-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="3e80b-119">GetLastError</span></span>](imapisession-getlasterror.md) <br/> |<span data-ttu-id="3e80b-120">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个会话错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3e80b-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous session error.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-121">GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="3e80b-121">GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md) <br/> |<span data-ttu-id="3e80b-122">提供对包含有关会话配置文件中的所有邮件存储区的信息的邮件存储表的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3e80b-122">Provides access to the message store table that contains information about all the message stores in the session profile.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-123">OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="3e80b-123">OpenMsgStore</span></span>](imapisession-openmsgstore.md) <br/> |<span data-ttu-id="3e80b-124">打开邮件存储, 并返回一个[IMsgStore](imsgstoreimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="3e80b-124">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-125">OpenAddressBook</span><span class="sxs-lookup"><span data-stu-id="3e80b-125">OpenAddressBook</span></span>](imapisession-openaddressbook.md) <br/> |<span data-ttu-id="3e80b-126">打开 MAPI 集成通讯簿, 返回一个[IAddrBook](iaddrbookimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="3e80b-126">Opens the MAPI integrated address book, returning an [IAddrBook](iaddrbookimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-127">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="3e80b-127">OpenProfileSection</span></span>](imapisession-openprofilesection.md) <br/> |<span data-ttu-id="3e80b-128">打开当前配置文件的一个部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="3e80b-128">Opens a section of the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-129">GetStatusTable</span><span class="sxs-lookup"><span data-stu-id="3e80b-129">GetStatusTable</span></span>](imapisession-getstatustable.md) <br/> |<span data-ttu-id="3e80b-130">提供对状态表的访问, 该表包含有关会话中所有 MAPI 资源的信息。</span><span class="sxs-lookup"><span data-stu-id="3e80b-130">Provides access to the status table, a table that contains information about all the MAPI resources in the session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-131">OpenEntry</span><span class="sxs-lookup"><span data-stu-id="3e80b-131">OpenEntry</span></span>](imapisession-openentry.md) <br/> |<span data-ttu-id="3e80b-132">打开一个对象并返回一个接口指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="3e80b-132">Opens an object and returns an interface pointer for further access.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-133">CompareEntryIDs</span><span class="sxs-lookup"><span data-stu-id="3e80b-133">CompareEntryIDs</span></span>](imapisession-compareentryids.md) <br/> |<span data-ttu-id="3e80b-134">对两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="3e80b-134">Compares two entry identifiers to determine whether they refer to the same object.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-135">她们</span><span class="sxs-lookup"><span data-stu-id="3e80b-135">Advise</span></span>](imapisession-advise.md) <br/> |<span data-ttu-id="3e80b-136">注册以接收影响会话的指定事件的通知。</span><span class="sxs-lookup"><span data-stu-id="3e80b-136">Registers to receive notification of specified events that affect the session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-137">Unadvise</span><span class="sxs-lookup"><span data-stu-id="3e80b-137">Unadvise</span></span>](imapisession-unadvise.md) <br/> |<span data-ttu-id="3e80b-138">取消以前使用对**Advise**方法的调用设置的通知发送。</span><span class="sxs-lookup"><span data-stu-id="3e80b-138">Cancels the sending of notifications previously set up with a call to the **Advise** method.</span></span>  <br/> |
|<span data-ttu-id="3e80b-139">**MessageOptions**</span><span class="sxs-lookup"><span data-stu-id="3e80b-139">**MessageOptions**</span></span> <br/> | <span data-ttu-id="3e80b-140">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e80b-140">*Not supported or documented.*</span></span>  <br/> |
|<span data-ttu-id="3e80b-141">**QueryDefaultMessageOpt**</span><span class="sxs-lookup"><span data-stu-id="3e80b-141">**QueryDefaultMessageOpt**</span></span> <br/> | <span data-ttu-id="3e80b-142">*不支持或记录。*</span><span class="sxs-lookup"><span data-stu-id="3e80b-142">*Not supported or documented.*</span></span>  <br/> |
|[<span data-ttu-id="3e80b-143">EnumAdrTypes</span><span class="sxs-lookup"><span data-stu-id="3e80b-143">EnumAdrTypes</span></span>](imapisession-enumadrtypes.md) <br/> |<span data-ttu-id="3e80b-144">已弃用。</span><span class="sxs-lookup"><span data-stu-id="3e80b-144">Deprecated.</span></span> <span data-ttu-id="3e80b-145">返回会话中的所有传输提供程序可以处理的地址类型。</span><span class="sxs-lookup"><span data-stu-id="3e80b-145">Returns the address types that can be handled by all of the transport providers in the session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-146">QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="3e80b-146">QueryIdentity</span></span>](imapisession-queryidentity.md) <br/> |<span data-ttu-id="3e80b-147">返回为会话提供主要标识的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3e80b-147">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-148">注销</span><span class="sxs-lookup"><span data-stu-id="3e80b-148">Logoff</span></span>](imapisession-logoff.md) <br/> |<span data-ttu-id="3e80b-149">结束 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="3e80b-149">Ends a MAPI session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-150">SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="3e80b-150">SetDefaultStore</span></span>](imapisession-setdefaultstore.md) <br/> |<span data-ttu-id="3e80b-151">将邮件存储区建立为会话的默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="3e80b-151">Establishes a message store as the default message store for the session.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-152">AdminServices</span><span class="sxs-lookup"><span data-stu-id="3e80b-152">AdminServices</span></span>](imapisession-adminservices.md) <br/> |<span data-ttu-id="3e80b-153">返回用于对邮件服务进行更改的[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。</span><span class="sxs-lookup"><span data-stu-id="3e80b-153">Returns an [IMsgServiceAdmin](imsgserviceadminiunknown.md) pointer for making changes to message services.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-154">ShowForm</span><span class="sxs-lookup"><span data-stu-id="3e80b-154">ShowForm</span></span>](imapisession-showform.md) <br/> |<span data-ttu-id="3e80b-155">显示窗体。</span><span class="sxs-lookup"><span data-stu-id="3e80b-155">Displays a form.</span></span>  <br/> |
|[<span data-ttu-id="3e80b-156">PrepareForm</span><span class="sxs-lookup"><span data-stu-id="3e80b-156">PrepareForm</span></span>](imapisession-prepareform.md) <br/> |<span data-ttu-id="3e80b-157">创建一个数字标记, **ShowForm**方法使用该标记来访问邮件。</span><span class="sxs-lookup"><span data-stu-id="3e80b-157">Creates a numeric token that the **ShowForm** method uses to access a message.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3e80b-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e80b-158">See also</span></span>



[<span data-ttu-id="3e80b-159">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="3e80b-159">MAPI Interfaces</span></span>](mapi-interfaces.md)

