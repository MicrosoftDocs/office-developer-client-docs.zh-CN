---
title: 消息存储提供程序必需的和可选接口
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc62e57e-82a4-4f37-8d1b-7cdf828b951e
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: d8cd03fa184865446da48d7532764ba71e0e47d4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778615"
---
# <a name="required-and-optional-interfaces-for-message-store-providers"></a><span data-ttu-id="36766-103">消息存储提供程序必需的和可选接口</span><span class="sxs-lookup"><span data-stu-id="36766-103">Required and Optional Interfaces for Message Store Providers</span></span>

 
  
<span data-ttu-id="36766-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="36766-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="36766-105">MAPI 定义一组与消息存储提供程序相关的接口。</span><span class="sxs-lookup"><span data-stu-id="36766-105">MAPI defines a set of interfaces that relate to message store providers.</span></span> <span data-ttu-id="36766-106">由于广泛的消息存储可以选择实现的功能，这些接口一些需要和某些不是。</span><span class="sxs-lookup"><span data-stu-id="36766-106">Because of the wide range of features that a message store can choose to implement, some of these interfaces are required and some are not.</span></span> <span data-ttu-id="36766-107">下表列出了对消息存储提供程序相关的 MAPI 接口，指定是否接口是必需或可选的并描述及其用途。</span><span class="sxs-lookup"><span data-stu-id="36766-107">The following table lists the MAPI interfaces that are related to message store providers, specifies whether the interfaces are required or optional, and describes their purpose.</span></span>
  
|<span data-ttu-id="36766-108">**接口**</span><span class="sxs-lookup"><span data-stu-id="36766-108">**Interface**</span></span>|<span data-ttu-id="36766-109">**Status**</span><span class="sxs-lookup"><span data-stu-id="36766-109">**Status**</span></span>|<span data-ttu-id="36766-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="36766-110">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="36766-111">IMSProvider</span><span class="sxs-lookup"><span data-stu-id="36766-111">IMSProvider</span></span>](imsprovideriunknown.md) <br/> |<span data-ttu-id="36766-112">必需</span><span class="sxs-lookup"><span data-stu-id="36766-112">Required</span></span>  <br/> |<span data-ttu-id="36766-113">登录到移开的消息存储。</span><span class="sxs-lookup"><span data-stu-id="36766-113">Logs on to and off of a message store.</span></span>  <br/> |
|[<span data-ttu-id="36766-114">IMSLogon</span><span class="sxs-lookup"><span data-stu-id="36766-114">IMSLogon</span></span>](imslogoniunknown.md) <br/> |<span data-ttu-id="36766-115">必需</span><span class="sxs-lookup"><span data-stu-id="36766-115">Required</span></span>  <br/> |<span data-ttu-id="36766-116">打开文件夹或消息，验证的消息存储的标识，并处理通知。</span><span class="sxs-lookup"><span data-stu-id="36766-116">Opens folders or messages, verifies the message store's identity, and handles notifications.</span></span>  <br/> |
|[<span data-ttu-id="36766-117">IMsgStore</span><span class="sxs-lookup"><span data-stu-id="36766-117">IMsgStore</span></span>](imsgstoreimapiprop.md) <br/> |<span data-ttu-id="36766-118">必需</span><span class="sxs-lookup"><span data-stu-id="36766-118">Required</span></span>  <br/> |<span data-ttu-id="36766-119">打开文件夹或消息，找到特殊文件夹，并处理的邮件提交。</span><span class="sxs-lookup"><span data-stu-id="36766-119">Opens folders or messages, finds special folders, and handles message submissions.</span></span>  <br/> |
|[<span data-ttu-id="36766-120">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="36766-120">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="36766-121">必需</span><span class="sxs-lookup"><span data-stu-id="36766-121">Required</span></span>  <br/> |<span data-ttu-id="36766-122">查找和处理消息和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="36766-122">Finds and manipulates messages and subfolders.</span></span>  <br/> |
|[<span data-ttu-id="36766-123">IMessage</span><span class="sxs-lookup"><span data-stu-id="36766-123">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="36766-124">必需</span><span class="sxs-lookup"><span data-stu-id="36766-124">Required</span></span>  <br/> |<span data-ttu-id="36766-125">处理附件，并设置的一些消息的属性。</span><span class="sxs-lookup"><span data-stu-id="36766-125">Manipulates attachments and sets some of a message's properties.</span></span>  <br/> |
|[<span data-ttu-id="36766-126">IMAPITable</span><span class="sxs-lookup"><span data-stu-id="36766-126">IMAPITable</span></span>](imapitableiunknown.md) <br/> |<span data-ttu-id="36766-127">必需</span><span class="sxs-lookup"><span data-stu-id="36766-127">Required</span></span>  <br/> |<span data-ttu-id="36766-128">允许其他对象来提供与各种 MAPI 组件的数据的集合。</span><span class="sxs-lookup"><span data-stu-id="36766-128">Enables other objects to present collections of data to various MAPI components.</span></span>  <br/> |
|[<span data-ttu-id="36766-129">IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="36766-129">IMAPIStatus</span></span>](imapistatusimapiprop.md) <br/> |<span data-ttu-id="36766-130">必需</span><span class="sxs-lookup"><span data-stu-id="36766-130">Required</span></span>  <br/> |<span data-ttu-id="36766-131">使客户端验证的消息存储的状态和执行一些配置任务。</span><span class="sxs-lookup"><span data-stu-id="36766-131">Enables clients to validate the state of a message store and to perform some configuration tasks.</span></span>  <br/> |
|[<span data-ttu-id="36766-132">IAttach</span><span class="sxs-lookup"><span data-stu-id="36766-132">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="36766-133">可选</span><span class="sxs-lookup"><span data-stu-id="36766-133">Optional</span></span>  <br/> |<span data-ttu-id="36766-134">如果存储提供程序支持的文件附件，则访问邮件附件属性。</span><span class="sxs-lookup"><span data-stu-id="36766-134">Accesses message attachment properties if the store provider supports file attachments.</span></span>  <br/> |
|<span data-ttu-id="36766-135">**IStorage**</span><span class="sxs-lookup"><span data-stu-id="36766-135">**IStorage**</span></span> <br/> |<span data-ttu-id="36766-136">可选</span><span class="sxs-lookup"><span data-stu-id="36766-136">Optional</span></span>  <br/> |<span data-ttu-id="36766-137">如果存储提供程序支持 OLE 对象附件，管理结构化的存储对象。</span><span class="sxs-lookup"><span data-stu-id="36766-137">Manages structured storage objects if the store provider supports OLE object attachments.</span></span>  <br/> |
|<span data-ttu-id="36766-138">**IStream**</span><span class="sxs-lookup"><span data-stu-id="36766-138">**IStream**</span></span> <br/> |<span data-ttu-id="36766-139">可选</span><span class="sxs-lookup"><span data-stu-id="36766-139">Optional</span></span>  <br/> |<span data-ttu-id="36766-140">启用邮件和附件对象以读取和写入 stream 对象的数据。</span><span class="sxs-lookup"><span data-stu-id="36766-140">Enables message and attachment objects to read and write data to stream objects.</span></span>  <br/> |
|<span data-ttu-id="36766-141">**IStreamDocfile**</span><span class="sxs-lookup"><span data-stu-id="36766-141">**IStreamDocfile**</span></span> <br/> |<span data-ttu-id="36766-142">可选</span><span class="sxs-lookup"><span data-stu-id="36766-142">Optional</span></span>  <br/> |<span data-ttu-id="36766-143">使某些服务提供商，以打开存储对象，例如复合文件中的 OLE 2.0 文件格式。</span><span class="sxs-lookup"><span data-stu-id="36766-143">Enables some service providers to open a storage object, such as a compound file in the OLE 2.0 file format.</span></span>  <br/> |
   
<span data-ttu-id="36766-144">您需要实现**IMAPIFolder**、 **IMessage**、 **IMAPIStatus**和**IMAPITable**的基本信息介绍了这些接口的参考主题。</span><span class="sxs-lookup"><span data-stu-id="36766-144">The basic information you need to implement **IMAPIFolder**, **IMessage**, **IMAPIStatus**, and **IMAPITable** is documented in the reference topics for these interfaces.</span></span> <span data-ttu-id="36766-145">本节包含与消息存储提供程序更直接相关的补充信息。</span><span class="sxs-lookup"><span data-stu-id="36766-145">This section contains supplementary information that is more directly related to message store providers.</span></span> <span data-ttu-id="36766-146">MAPI 接口的其余部分应实现根据本节中和相应的参考主题中的信息。</span><span class="sxs-lookup"><span data-stu-id="36766-146">The rest of the MAPI interfaces should be implemented according to the information in this section and in the appropriate reference topics.</span></span> <span data-ttu-id="36766-147">请参阅有关实施**IStorage**、 **IStream**和**IStreamDocFile**Windows SDK 中的 COM 和 ActiveX 对象服务部分。</span><span class="sxs-lookup"><span data-stu-id="36766-147">See the COM and ActiveX Object Services section in the Windows SDK for more information about implementing **IStorage**, **IStream**, and **IStreamDocFile**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36766-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36766-148">See also</span></span>



[<span data-ttu-id="36766-149">开发 MAPI 消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="36766-149">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

