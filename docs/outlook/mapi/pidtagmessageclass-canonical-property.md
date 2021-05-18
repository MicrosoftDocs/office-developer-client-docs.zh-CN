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
ms.openlocfilehash: 7912a3831333ff8a464a12e567430eb5a3272172
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359261"
---
# <a name="pidtagmessageclass-canonical-property"></a><span data-ttu-id="ff8e6-103">PidTagMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff8e6-103">PidTagMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="ff8e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff8e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff8e6-105">包含标识发件人定义的消息类别的文本字符串，例如 IPM.Note。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-105">Contains a text string that identifies the sender-defined message class, such as IPM.Note.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ff8e6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ff8e6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff8e6-107">PR_MESSAGE_CLASS、PR_MESSAGE_CLASS_A、PR_MESSAGE_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="ff8e6-107">PR_MESSAGE_CLASS, PR_MESSAGE_CLASS_A, PR_MESSAGE_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="ff8e6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ff8e6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ff8e6-109">0x001A</span><span class="sxs-lookup"><span data-stu-id="ff8e6-109">0x001A</span></span>  <br/> |
|<span data-ttu-id="ff8e6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff8e6-110">Data type:</span></span>  <br/> |<span data-ttu-id="ff8e6-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="ff8e6-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="ff8e6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ff8e6-112">Area:</span></span>  <br/> |<span data-ttu-id="ff8e6-113">常见</span><span class="sxs-lookup"><span data-stu-id="ff8e6-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff8e6-114">备注</span><span class="sxs-lookup"><span data-stu-id="ff8e6-114">Remarks</span></span>

<span data-ttu-id="ff8e6-115">邮件类指定邮件的类型。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-115">The message class specifies the type of the message.</span></span> <span data-ttu-id="ff8e6-116">它确定为邮件定义的属性集、邮件传达的信息类型以及如何处理邮件。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-116">It determines the set of properties defined for the message, the kind of information the message conveys, and how to handle the message.</span></span> 
  
<span data-ttu-id="ff8e6-117">这些属性包含与句点连接在一起的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-117">These properties contain strings concatenated with periods.</span></span> <span data-ttu-id="ff8e6-118">每个字符串表示子类的级别。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-118">Each string represents a level of subclassing.</span></span> <span data-ttu-id="ff8e6-119">例如，IPM。注意 是 IPM 的子类和 IPM 的超级类。Note.Private。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-119">For example, IPM.Note is a subclass of IPM and a superclass of IPM.Note.Private.</span></span> 
  
<span data-ttu-id="ff8e6-120">这些属性必须由 32 到 127 的 ASCII 字符组成，不得以 ASCII 46 (结束) 。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-120">These properties must consist of the ASCII characters 32 through 127 and must not end with a period (ASCII 46).</span></span> <span data-ttu-id="ff8e6-121">排序和比较操作必须视为不区分大小写的字符串。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-121">Sort and compare operations must treat it as a case-insensitive string.</span></span> <span data-ttu-id="ff8e6-122">最大可能长度为 255 个字符，但为了允许 MAPI 会议室追加限定符，建议原始长度保持在 128 个字符以下。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-122">The maximum possible length is 255 characters, but in order to allow MAPI room to append qualifiers it is recommended that the original length be kept under 128 characters.</span></span> 
  
<span data-ttu-id="ff8e6-123">需要每条消息才能提供这些属性。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-123">Every message is required to furnish these properties.</span></span> <span data-ttu-id="ff8e6-124">通常，一旦 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 成功返回，创建新消息的客户端应用程序就会设置它。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-124">Normally, the client application creating a new message sets it as soon as [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) returns successfully.</span></span> <span data-ttu-id="ff8e6-125">但是，如果客户端调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md)时尚未设置该属性，则消息存储应将其设置为 IPM。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-125">But if the property has not been set when the client calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md), the message store should set it to IPM.</span></span> 
  
<span data-ttu-id="ff8e6-126">MAPI 定义的值为：</span><span class="sxs-lookup"><span data-stu-id="ff8e6-126">The values defined by MAPI are:</span></span> 
  
```cpp
IPM.Note for a standard interpersonal message 
REPORT.<subject message class>.DR for a delivery report 
REPORT.<subject message class>.NDR for a nondelivery report 
REPORT.<subject message class>.IPNRN for a read report 
REPORT.<subject message class>.IPNNRN for a nonread report 
 
```

<span data-ttu-id="ff8e6-127">IPM 和 IPC 仅用作超级类，邮件在存储或提交之前至少应附加一个子类限定符。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-127">IPM and IPC are intended to be superclasses only, and a message should have at least one subclass qualifier appended before being stored or submitted.</span></span> <span data-ttu-id="ff8e6-128">有关邮件类使用情况的信息，请参阅 [邮件类](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-128">For more information on message class usage, see [Message Classes](mapi-message-classes.md).</span></span> <span data-ttu-id="ff8e6-129">有关邮件类的必需属性和可选属性的列表，请参阅关于邮件 [属性的子标题](message-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-129">For lists of required and optional properties for message classes, see the subtopics of [About Message Properties](message-properties-overview.md).</span></span>
  
<span data-ttu-id="ff8e6-130">自定义邮件类可以定义保留范围中的属性，以仅与邮件类一同使用。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-130">A custom message class can define properties in a reserved range for use with that message class only.</span></span> <span data-ttu-id="ff8e6-131">有关详细信息，请参阅关于 [属性标识符](mapi-property-identifier-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-131">For more information, see [About Property Identifiers](mapi-property-identifier-overview.md).</span></span> 
  
<span data-ttu-id="ff8e6-132">邮件类控制传入邮件存储在哪个接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-132">Message classes control which receive folder an incoming message is stored in.</span></span> <span data-ttu-id="ff8e6-133">有关详细信息，请参阅 [IMsgStore：：GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-133">For more information, see the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> 
  
<span data-ttu-id="ff8e6-134">有关将邮件类与窗体和窗体服务器一同使用的信息，请参阅 [选择邮件类](choosing-a-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-134">For more information on using message classes with forms and form servers, see [Choosing a Message Class](choosing-a-message-class.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ff8e6-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff8e6-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ff8e6-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="ff8e6-136">Protocol specifications</span></span>

<span data-ttu-id="ff8e6-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff8e6-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff8e6-138">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-138">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ff8e6-139">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff8e6-139">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff8e6-140">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-140">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ff8e6-141">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff8e6-141">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff8e6-142">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-142">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="ff8e6-143">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ff8e6-143">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ff8e6-144">指定允许用于表示语音邮件和传真邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-144">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ff8e6-145">头文件</span><span class="sxs-lookup"><span data-stu-id="ff8e6-145">Header files</span></span>

<span data-ttu-id="ff8e6-146">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff8e6-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff8e6-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="ff8e6-148">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ff8e6-148">Mapitags.h</span></span>
  
> <span data-ttu-id="ff8e6-149">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ff8e6-149">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff8e6-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff8e6-150">See also</span></span>



[<span data-ttu-id="ff8e6-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff8e6-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff8e6-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff8e6-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff8e6-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ff8e6-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff8e6-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff8e6-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

