---
title: 邮件存储提供程序的必需接口和可选接口
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc62e57e-82a4-4f37-8d1b-7cdf828b951e
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 35b1d05d742b0d8defabf84b6dbf7d418ece0bbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420918"
---
# <a name="required-and-optional-interfaces-for-message-store-providers"></a><span data-ttu-id="3debd-103">邮件存储提供程序的必需接口和可选接口</span><span class="sxs-lookup"><span data-stu-id="3debd-103">Required and Optional Interfaces for Message Store Providers</span></span>

 
  
<span data-ttu-id="3debd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3debd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3debd-105">MAPI 定义一组与邮件存储提供程序相关的接口。</span><span class="sxs-lookup"><span data-stu-id="3debd-105">MAPI defines a set of interfaces that relate to message store providers.</span></span> <span data-ttu-id="3debd-106">由于邮件存储可以选择实现各种功能，因此其中一些接口是必需的，有些则不是。</span><span class="sxs-lookup"><span data-stu-id="3debd-106">Because of the wide range of features that a message store can choose to implement, some of these interfaces are required and some are not.</span></span> <span data-ttu-id="3debd-107">下表列出了与邮件存储提供程序相关的 MAPI 接口，指定了这些接口是必需接口还是可选接口，并描述了它们的用途。</span><span class="sxs-lookup"><span data-stu-id="3debd-107">The following table lists the MAPI interfaces that are related to message store providers, specifies whether the interfaces are required or optional, and describes their purpose.</span></span>
  
|<span data-ttu-id="3debd-108">**接口**</span><span class="sxs-lookup"><span data-stu-id="3debd-108">**Interface**</span></span>|<span data-ttu-id="3debd-109">**状态**</span><span class="sxs-lookup"><span data-stu-id="3debd-109">**Status**</span></span>|<span data-ttu-id="3debd-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="3debd-110">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3debd-111">IMSProvider</span><span class="sxs-lookup"><span data-stu-id="3debd-111">IMSProvider</span></span>](imsprovideriunknown.md) <br/> |<span data-ttu-id="3debd-112">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-112">Required</span></span>  <br/> |<span data-ttu-id="3debd-113">登录到和注销邮件存储。</span><span class="sxs-lookup"><span data-stu-id="3debd-113">Logs on to and off of a message store.</span></span>  <br/> |
|[<span data-ttu-id="3debd-114">IMSLogon</span><span class="sxs-lookup"><span data-stu-id="3debd-114">IMSLogon</span></span>](imslogoniunknown.md) <br/> |<span data-ttu-id="3debd-115">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-115">Required</span></span>  <br/> |<span data-ttu-id="3debd-116">打开文件夹或邮件，验证邮件存储的标识并处理通知。</span><span class="sxs-lookup"><span data-stu-id="3debd-116">Opens folders or messages, verifies the message store's identity, and handles notifications.</span></span>  <br/> |
|[<span data-ttu-id="3debd-117">IMsgStore</span><span class="sxs-lookup"><span data-stu-id="3debd-117">IMsgStore</span></span>](imsgstoreimapiprop.md) <br/> |<span data-ttu-id="3debd-118">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-118">Required</span></span>  <br/> |<span data-ttu-id="3debd-119">打开文件夹或邮件，查找特殊文件夹，并处理邮件提交。</span><span class="sxs-lookup"><span data-stu-id="3debd-119">Opens folders or messages, finds special folders, and handles message submissions.</span></span>  <br/> |
|[<span data-ttu-id="3debd-120">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="3debd-120">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="3debd-121">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-121">Required</span></span>  <br/> |<span data-ttu-id="3debd-122">查找和处理消息和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="3debd-122">Finds and manipulates messages and subfolders.</span></span>  <br/> |
|[<span data-ttu-id="3debd-123">IMessage</span><span class="sxs-lookup"><span data-stu-id="3debd-123">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="3debd-124">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-124">Required</span></span>  <br/> |<span data-ttu-id="3debd-125">操作附件并设置邮件的一些属性。</span><span class="sxs-lookup"><span data-stu-id="3debd-125">Manipulates attachments and sets some of a message's properties.</span></span>  <br/> |
|[<span data-ttu-id="3debd-126">IMAPITable</span><span class="sxs-lookup"><span data-stu-id="3debd-126">IMAPITable</span></span>](imapitableiunknown.md) <br/> |<span data-ttu-id="3debd-127">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-127">Required</span></span>  <br/> |<span data-ttu-id="3debd-128">允许其他对象向各种 MAPI 组件显示数据集合。</span><span class="sxs-lookup"><span data-stu-id="3debd-128">Enables other objects to present collections of data to various MAPI components.</span></span>  <br/> |
|[<span data-ttu-id="3debd-129">IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="3debd-129">IMAPIStatus</span></span>](imapistatusimapiprop.md) <br/> |<span data-ttu-id="3debd-130">必需</span><span class="sxs-lookup"><span data-stu-id="3debd-130">Required</span></span>  <br/> |<span data-ttu-id="3debd-131">使客户端能够验证邮件存储的状态并执行一些配置任务。</span><span class="sxs-lookup"><span data-stu-id="3debd-131">Enables clients to validate the state of a message store and to perform some configuration tasks.</span></span>  <br/> |
|[<span data-ttu-id="3debd-132">IAttach</span><span class="sxs-lookup"><span data-stu-id="3debd-132">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="3debd-133">可选</span><span class="sxs-lookup"><span data-stu-id="3debd-133">Optional</span></span>  <br/> |<span data-ttu-id="3debd-134">如果存储提供程序支持文件附件，则访问邮件附件属性。</span><span class="sxs-lookup"><span data-stu-id="3debd-134">Accesses message attachment properties if the store provider supports file attachments.</span></span>  <br/> |
|<span data-ttu-id="3debd-135">**IStorage**</span><span class="sxs-lookup"><span data-stu-id="3debd-135">**IStorage**</span></span> <br/> |<span data-ttu-id="3debd-136">可选</span><span class="sxs-lookup"><span data-stu-id="3debd-136">Optional</span></span>  <br/> |<span data-ttu-id="3debd-137">如果存储提供程序支持 OLE 对象附件，则管理结构化存储对象。</span><span class="sxs-lookup"><span data-stu-id="3debd-137">Manages structured storage objects if the store provider supports OLE object attachments.</span></span>  <br/> |
|<span data-ttu-id="3debd-138">**IStream**</span><span class="sxs-lookup"><span data-stu-id="3debd-138">**IStream**</span></span> <br/> |<span data-ttu-id="3debd-139">可选</span><span class="sxs-lookup"><span data-stu-id="3debd-139">Optional</span></span>  <br/> |<span data-ttu-id="3debd-140">使邮件和附件对象能够读取数据以及将数据写入流对象。</span><span class="sxs-lookup"><span data-stu-id="3debd-140">Enables message and attachment objects to read and write data to stream objects.</span></span>  <br/> |
|<span data-ttu-id="3debd-141">**IStreamDocfile**</span><span class="sxs-lookup"><span data-stu-id="3debd-141">**IStreamDocfile**</span></span> <br/> |<span data-ttu-id="3debd-142">可选</span><span class="sxs-lookup"><span data-stu-id="3debd-142">Optional</span></span>  <br/> |<span data-ttu-id="3debd-143">允许某些服务提供商打开存储对象，例如 OLE 2.0 文件格式的复合文件。</span><span class="sxs-lookup"><span data-stu-id="3debd-143">Enables some service providers to open a storage object, such as a compound file in the OLE 2.0 file format.</span></span>  <br/> |
   
<span data-ttu-id="3debd-144">这些接口的参考主题中记录了实现 IMAPIFolder、IMessage、IMAPIStatus 和 **IMAPITable** 所需的基本信息。   </span><span class="sxs-lookup"><span data-stu-id="3debd-144">The basic information you need to implement **IMAPIFolder**, **IMessage**, **IMAPIStatus**, and **IMAPITable** is documented in the reference topics for these interfaces.</span></span> <span data-ttu-id="3debd-145">本节包含与邮件存储提供程序更直接相关的补充信息。</span><span class="sxs-lookup"><span data-stu-id="3debd-145">This section contains supplementary information that is more directly related to message store providers.</span></span> <span data-ttu-id="3debd-146">其余 MAPI 接口应按照本节和相应参考主题的信息实现。</span><span class="sxs-lookup"><span data-stu-id="3debd-146">The rest of the MAPI interfaces should be implemented according to the information in this section and in the appropriate reference topics.</span></span> <span data-ttu-id="3debd-147">有关实现 **IStorage、IStream** 和 **IStreamDocFile** Windows，请参阅 Windows SDK 中的COM 和 ActiveX 对象服务部分。</span><span class="sxs-lookup"><span data-stu-id="3debd-147">See the COM and ActiveX Object Services section in the Windows SDK for more information about implementing **IStorage**, **IStream**, and **IStreamDocFile**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3debd-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3debd-148">See also</span></span>



[<span data-ttu-id="3debd-149">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="3debd-149">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

