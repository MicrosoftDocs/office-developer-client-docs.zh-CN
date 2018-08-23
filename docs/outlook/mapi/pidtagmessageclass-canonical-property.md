---
title: PidTagMessageClass 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageClass
api_type:
- HeaderDef
ms.assetid: 1e704023-1992-4b43-857e-0a7da7bc8e87
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f54bdb70e9f48c89cb50e8238f8638deac8a93b0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567816"
---
# <a name="pidtagmessageclass-canonical-property"></a><span data-ttu-id="24c79-103">PidTagMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="24c79-103">PidTagMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="24c79-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24c79-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24c79-105">包含标识-定义发件人的邮件类 IPM 如文本字符串。请注意。</span><span class="sxs-lookup"><span data-stu-id="24c79-105">Contains a text string that identifies the sender-defined message class, such as IPM.Note.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="24c79-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="24c79-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="24c79-107">PR_MESSAGE_CLASS，PR_MESSAGE_CLASS_A，PR_MESSAGE_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="24c79-107">PR_MESSAGE_CLASS, PR_MESSAGE_CLASS_A, PR_MESSAGE_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="24c79-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="24c79-108">Identifier:</span></span>  <br/> |<span data-ttu-id="24c79-109">0x001A</span><span class="sxs-lookup"><span data-stu-id="24c79-109">0x001A</span></span>  <br/> |
|<span data-ttu-id="24c79-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="24c79-110">Data type:</span></span>  <br/> |<span data-ttu-id="24c79-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="24c79-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="24c79-112">区域：</span><span class="sxs-lookup"><span data-stu-id="24c79-112">Area:</span></span>  <br/> |<span data-ttu-id="24c79-113">Common</span><span class="sxs-lookup"><span data-stu-id="24c79-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="24c79-114">注解</span><span class="sxs-lookup"><span data-stu-id="24c79-114">Remarks</span></span>

<span data-ttu-id="24c79-115">邮件类将指定的邮件的类型。</span><span class="sxs-lookup"><span data-stu-id="24c79-115">The message class specifies the type of the message.</span></span> <span data-ttu-id="24c79-116">它确定属性为邮件，定义将传达信息消息的类型，以及如何处理邮件的设置。</span><span class="sxs-lookup"><span data-stu-id="24c79-116">It determines the set of properties defined for the message, the kind of information the message conveys, and how to handle the message.</span></span> 
  
<span data-ttu-id="24c79-117">这些属性包含与阶段连接在一起的字符串。</span><span class="sxs-lookup"><span data-stu-id="24c79-117">These properties contain strings concatenated with periods.</span></span> <span data-ttu-id="24c79-118">每个字符串代表子类的一个级别。</span><span class="sxs-lookup"><span data-stu-id="24c79-118">Each string represents a level of subclassing.</span></span> <span data-ttu-id="24c79-119">例如，IPM。注意是 IPM 的 IPM 的一个子类和超类别。Note.Private。</span><span class="sxs-lookup"><span data-stu-id="24c79-119">For example, IPM.Note is a subclass of IPM and a superclass of IPM.Note.Private.</span></span> 
  
<span data-ttu-id="24c79-120">这些属性必须包括 ASCII 字符到 127 32，并且必须以句点 (ASCII 46) 结尾。</span><span class="sxs-lookup"><span data-stu-id="24c79-120">These properties must consist of the ASCII characters 32 through 127 and must not end with a period (ASCII 46).</span></span> <span data-ttu-id="24c79-121">排序和比较操作必须将其视为不区分大小写的字符串。</span><span class="sxs-lookup"><span data-stu-id="24c79-121">Sort and compare operations must treat it as a case-insensitive string.</span></span> <span data-ttu-id="24c79-122">可能的最大长度为 255 个字符，但为了允许 MAPI 会议室追加限定符建议的原始长度保存下 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="24c79-122">The maximum possible length is 255 characters, but in order to allow MAPI room to append qualifiers it is recommended that the original length be kept under 128 characters.</span></span> 
  
<span data-ttu-id="24c79-123">每个邮件需要提供这些属性。</span><span class="sxs-lookup"><span data-stu-id="24c79-123">Every message is required to furnish these properties.</span></span> <span data-ttu-id="24c79-124">通常，创建一个新的邮件的客户端应用程序将其设置为[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)成功返回。</span><span class="sxs-lookup"><span data-stu-id="24c79-124">Normally, the client application creating a new message sets it as soon as [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) returns successfully.</span></span> <span data-ttu-id="24c79-125">但是，如果尚未设置该属性，当客户端调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)，消息存储应将其设置为 IPM。</span><span class="sxs-lookup"><span data-stu-id="24c79-125">But if the property has not been set when the client calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md), the message store should set it to IPM.</span></span> 
  
<span data-ttu-id="24c79-126">由 MAPI 定义的值是：</span><span class="sxs-lookup"><span data-stu-id="24c79-126">The values defined by MAPI are:</span></span> 
  
```cpp
IPM.Note for a standard interpersonal message 
REPORT.<subject message class>.DR for a delivery report 
REPORT.<subject message class>.NDR for a nondelivery report 
REPORT.<subject message class>.IPNRN for a read report 
REPORT.<subject message class>.IPNNRN for a nonread report 
 
```

<span data-ttu-id="24c79-127">IPM 和 IPC 都应是超类仅，和一条消息，应具有至少一个要存储或提交之前追加的子类限定符。</span><span class="sxs-lookup"><span data-stu-id="24c79-127">IPM and IPC are intended to be superclasses only, and a message should have at least one subclass qualifier appended before being stored or submitted.</span></span> <span data-ttu-id="24c79-128">邮件类的用法的详细信息，请参阅[Message Classes](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="24c79-128">For more information on message class usage, see [Message Classes](mapi-message-classes.md).</span></span> <span data-ttu-id="24c79-129">对于邮件类的必需的和可选属性的列表，请参阅[关于消息属性](message-properties-overview.md)的副标题。</span><span class="sxs-lookup"><span data-stu-id="24c79-129">For lists of required and optional properties for message classes, see the subtopics of [About Message Properties](message-properties-overview.md).</span></span>
  
<span data-ttu-id="24c79-130">自定义邮件类别可用于该邮件类仅保留范围内定义属性。</span><span class="sxs-lookup"><span data-stu-id="24c79-130">A custom message class can define properties in a reserved range for use with that message class only.</span></span> <span data-ttu-id="24c79-131">有关详细信息，请参阅[有关属性标识符](mapi-property-identifier-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="24c79-131">For more information, see [About Property Identifiers](mapi-property-identifier-overview.md).</span></span> 
  
<span data-ttu-id="24c79-132">邮件类控件的接收文件夹传入消息存储在。</span><span class="sxs-lookup"><span data-stu-id="24c79-132">Message classes control which receive folder an incoming message is stored in.</span></span> <span data-ttu-id="24c79-133">有关详细信息，请参阅[IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="24c79-133">For more information, see the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> 
  
<span data-ttu-id="24c79-134">有关使用窗体和窗体服务器的邮件类的详细信息，请参阅[Choosing 邮件类](choosing-a-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="24c79-134">For more information on using message classes with forms and form servers, see [Choosing a Message Class](choosing-a-message-class.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="24c79-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="24c79-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="24c79-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="24c79-136">Protocol specifications</span></span>

<span data-ttu-id="24c79-137">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24c79-137">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24c79-138">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="24c79-138">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="24c79-139">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24c79-139">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24c79-140">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="24c79-140">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="24c79-141">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24c79-141">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24c79-142">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="24c79-142">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="24c79-143">[[MS OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="24c79-143">[[MS-OXOUM]](http://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="24c79-144">指定的属性和操作所允许的表示语音邮件和传真消息。</span><span class="sxs-lookup"><span data-stu-id="24c79-144">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="24c79-145">头文件</span><span class="sxs-lookup"><span data-stu-id="24c79-145">Header files</span></span>

<span data-ttu-id="24c79-146">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="24c79-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="24c79-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="24c79-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="24c79-148">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="24c79-148">Mapitags.h</span></span>
  
> <span data-ttu-id="24c79-149">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="24c79-149">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="24c79-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24c79-150">See also</span></span>



[<span data-ttu-id="24c79-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="24c79-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="24c79-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="24c79-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="24c79-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="24c79-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="24c79-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="24c79-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

