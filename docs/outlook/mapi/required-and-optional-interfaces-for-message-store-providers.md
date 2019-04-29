---
title: 邮件存储提供程序的必需和可选接口
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
# <a name="required-and-optional-interfaces-for-message-store-providers"></a><span data-ttu-id="bb290-103">邮件存储提供程序的必需和可选接口</span><span class="sxs-lookup"><span data-stu-id="bb290-103">Required and Optional Interfaces for Message Store Providers</span></span>

 
  
<span data-ttu-id="bb290-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb290-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb290-105">MAPI 定义了一组与邮件存储提供程序相关的接口。</span><span class="sxs-lookup"><span data-stu-id="bb290-105">MAPI defines a set of interfaces that relate to message store providers.</span></span> <span data-ttu-id="bb290-106">由于邮件存储区可以选择实现的功能范围很广, 因此某些接口是必需的, 而有些则不是。</span><span class="sxs-lookup"><span data-stu-id="bb290-106">Because of the wide range of features that a message store can choose to implement, some of these interfaces are required and some are not.</span></span> <span data-ttu-id="bb290-107">下表列出了与邮件存储提供程序相关的 MAPI 接口, 指定这些接口是必需的还是可选的, 并说明其用途。</span><span class="sxs-lookup"><span data-stu-id="bb290-107">The following table lists the MAPI interfaces that are related to message store providers, specifies whether the interfaces are required or optional, and describes their purpose.</span></span>
  
|<span data-ttu-id="bb290-108">**接口**</span><span class="sxs-lookup"><span data-stu-id="bb290-108">**Interface**</span></span>|<span data-ttu-id="bb290-109">**状态**</span><span class="sxs-lookup"><span data-stu-id="bb290-109">**Status**</span></span>|<span data-ttu-id="bb290-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="bb290-110">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="bb290-111">IMSProvider</span><span class="sxs-lookup"><span data-stu-id="bb290-111">IMSProvider</span></span>](imsprovideriunknown.md) <br/> |<span data-ttu-id="bb290-112">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-112">Required</span></span>  <br/> |<span data-ttu-id="bb290-113">登录和注销邮件存储。</span><span class="sxs-lookup"><span data-stu-id="bb290-113">Logs on to and off of a message store.</span></span>  <br/> |
|[<span data-ttu-id="bb290-114">IMSLogon</span><span class="sxs-lookup"><span data-stu-id="bb290-114">IMSLogon</span></span>](imslogoniunknown.md) <br/> |<span data-ttu-id="bb290-115">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-115">Required</span></span>  <br/> |<span data-ttu-id="bb290-116">打开文件夹或邮件, 验证邮件存储区的标识并处理通知。</span><span class="sxs-lookup"><span data-stu-id="bb290-116">Opens folders or messages, verifies the message store's identity, and handles notifications.</span></span>  <br/> |
|[<span data-ttu-id="bb290-117">IMsgStore</span><span class="sxs-lookup"><span data-stu-id="bb290-117">IMsgStore</span></span>](imsgstoreimapiprop.md) <br/> |<span data-ttu-id="bb290-118">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-118">Required</span></span>  <br/> |<span data-ttu-id="bb290-119">打开文件夹或邮件, 查找特殊文件夹并处理邮件提交。</span><span class="sxs-lookup"><span data-stu-id="bb290-119">Opens folders or messages, finds special folders, and handles message submissions.</span></span>  <br/> |
|[<span data-ttu-id="bb290-120">IMAPIFolder</span><span class="sxs-lookup"><span data-stu-id="bb290-120">IMAPIFolder</span></span>](imapifolderimapicontainer.md) <br/> |<span data-ttu-id="bb290-121">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-121">Required</span></span>  <br/> |<span data-ttu-id="bb290-122">查找并操纵邮件和子文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb290-122">Finds and manipulates messages and subfolders.</span></span>  <br/> |
|[<span data-ttu-id="bb290-123">IMessage</span><span class="sxs-lookup"><span data-stu-id="bb290-123">IMessage</span></span>](imessageimapiprop.md) <br/> |<span data-ttu-id="bb290-124">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-124">Required</span></span>  <br/> |<span data-ttu-id="bb290-125">操纵附件并设置邮件的一些属性。</span><span class="sxs-lookup"><span data-stu-id="bb290-125">Manipulates attachments and sets some of a message's properties.</span></span>  <br/> |
|[<span data-ttu-id="bb290-126">IMAPITable</span><span class="sxs-lookup"><span data-stu-id="bb290-126">IMAPITable</span></span>](imapitableiunknown.md) <br/> |<span data-ttu-id="bb290-127">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-127">Required</span></span>  <br/> |<span data-ttu-id="bb290-128">允许其他对象向各种 MAPI 组件提供数据集合。</span><span class="sxs-lookup"><span data-stu-id="bb290-128">Enables other objects to present collections of data to various MAPI components.</span></span>  <br/> |
|[<span data-ttu-id="bb290-129">IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="bb290-129">IMAPIStatus</span></span>](imapistatusimapiprop.md) <br/> |<span data-ttu-id="bb290-130">必需</span><span class="sxs-lookup"><span data-stu-id="bb290-130">Required</span></span>  <br/> |<span data-ttu-id="bb290-131">使客户端能够验证邮件存储的状态并执行某些配置任务。</span><span class="sxs-lookup"><span data-stu-id="bb290-131">Enables clients to validate the state of a message store and to perform some configuration tasks.</span></span>  <br/> |
|[<span data-ttu-id="bb290-132">IAttach</span><span class="sxs-lookup"><span data-stu-id="bb290-132">IAttach</span></span>](iattachimapiprop.md) <br/> |<span data-ttu-id="bb290-133">可选</span><span class="sxs-lookup"><span data-stu-id="bb290-133">Optional</span></span>  <br/> |<span data-ttu-id="bb290-134">如果存储提供程序支持文件附件, 则访问邮件附件属性。</span><span class="sxs-lookup"><span data-stu-id="bb290-134">Accesses message attachment properties if the store provider supports file attachments.</span></span>  <br/> |
|<span data-ttu-id="bb290-135">**IStorage**</span><span class="sxs-lookup"><span data-stu-id="bb290-135">**IStorage**</span></span> <br/> |<span data-ttu-id="bb290-136">可选</span><span class="sxs-lookup"><span data-stu-id="bb290-136">Optional</span></span>  <br/> |<span data-ttu-id="bb290-137">如果存储提供程序支持 OLE 对象附件, 则管理结构化存储对象。</span><span class="sxs-lookup"><span data-stu-id="bb290-137">Manages structured storage objects if the store provider supports OLE object attachments.</span></span>  <br/> |
|<span data-ttu-id="bb290-138">**IStream**</span><span class="sxs-lookup"><span data-stu-id="bb290-138">**IStream**</span></span> <br/> |<span data-ttu-id="bb290-139">可选</span><span class="sxs-lookup"><span data-stu-id="bb290-139">Optional</span></span>  <br/> |<span data-ttu-id="bb290-140">允许邮件和附件对象读取数据并将数据写入 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="bb290-140">Enables message and attachment objects to read and write data to stream objects.</span></span>  <br/> |
|<span data-ttu-id="bb290-141">**IStreamDocfile**</span><span class="sxs-lookup"><span data-stu-id="bb290-141">**IStreamDocfile**</span></span> <br/> |<span data-ttu-id="bb290-142">可选</span><span class="sxs-lookup"><span data-stu-id="bb290-142">Optional</span></span>  <br/> |<span data-ttu-id="bb290-143">使某些服务提供程序能够打开存储对象, 如 OLE 2.0 文件格式的复合文件。</span><span class="sxs-lookup"><span data-stu-id="bb290-143">Enables some service providers to open a storage object, such as a compound file in the OLE 2.0 file format.</span></span>  <br/> |
   
<span data-ttu-id="bb290-144">在这些接口的参考主题中记录了实现**IMAPIFolder**、 **IMessage**、 **IMAPIStatus**和**IMAPITable**所需的基本信息。</span><span class="sxs-lookup"><span data-stu-id="bb290-144">The basic information you need to implement **IMAPIFolder**, **IMessage**, **IMAPIStatus**, and **IMAPITable** is documented in the reference topics for these interfaces.</span></span> <span data-ttu-id="bb290-145">本节包含与邮件存储提供程序更直接相关的补充信息。</span><span class="sxs-lookup"><span data-stu-id="bb290-145">This section contains supplementary information that is more directly related to message store providers.</span></span> <span data-ttu-id="bb290-146">应按照本节中的信息和相应的参考主题来实施 MAPI 接口的其余部分。</span><span class="sxs-lookup"><span data-stu-id="bb290-146">The rest of the MAPI interfaces should be implemented according to the information in this section and in the appropriate reference topics.</span></span> <span data-ttu-id="bb290-147">有关实现**IStorage**、 **IStream**和**IStreamDocFile**的详细信息, 请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。</span><span class="sxs-lookup"><span data-stu-id="bb290-147">See the COM and ActiveX Object Services section in the Windows SDK for more information about implementing **IStorage**, **IStream**, and **IStreamDocFile**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb290-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb290-148">See also</span></span>



[<span data-ttu-id="bb290-149">开发 MAPI 邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="bb290-149">Developing a MAPI Message Store Provider</span></span>](developing-a-mapi-message-store-provider.md)

