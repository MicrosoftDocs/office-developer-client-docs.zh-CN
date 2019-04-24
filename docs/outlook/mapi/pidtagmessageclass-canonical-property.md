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
# <a name="pidtagmessageclass-canonical-property"></a><span data-ttu-id="348e0-103">PidTagMessageClass 规范属性</span><span class="sxs-lookup"><span data-stu-id="348e0-103">PidTagMessageClass Canonical Property</span></span>

  
  
<span data-ttu-id="348e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="348e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="348e0-105">包含标识发件人定义的邮件类 (如 IPM) 的文本字符串。便笺.</span><span class="sxs-lookup"><span data-stu-id="348e0-105">Contains a text string that identifies the sender-defined message class, such as IPM.Note.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="348e0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="348e0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="348e0-107">PR_MESSAGE_CLASS、PR_MESSAGE_CLASS_A、PR_MESSAGE_CLASS_W</span><span class="sxs-lookup"><span data-stu-id="348e0-107">PR_MESSAGE_CLASS, PR_MESSAGE_CLASS_A, PR_MESSAGE_CLASS_W</span></span>  <br/> |
|<span data-ttu-id="348e0-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="348e0-108">Identifier:</span></span>  <br/> |<span data-ttu-id="348e0-109">0x001A</span><span class="sxs-lookup"><span data-stu-id="348e0-109">0x001A</span></span>  <br/> |
|<span data-ttu-id="348e0-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="348e0-110">Data type:</span></span>  <br/> |<span data-ttu-id="348e0-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="348e0-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="348e0-112">区域：</span><span class="sxs-lookup"><span data-stu-id="348e0-112">Area:</span></span>  <br/> |<span data-ttu-id="348e0-113">常见</span><span class="sxs-lookup"><span data-stu-id="348e0-113">Common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="348e0-114">注解</span><span class="sxs-lookup"><span data-stu-id="348e0-114">Remarks</span></span>

<span data-ttu-id="348e0-115">邮件类指定邮件的类型。</span><span class="sxs-lookup"><span data-stu-id="348e0-115">The message class specifies the type of the message.</span></span> <span data-ttu-id="348e0-116">它确定为邮件定义的属性集、邮件所传达的信息类型以及处理邮件的方式。</span><span class="sxs-lookup"><span data-stu-id="348e0-116">It determines the set of properties defined for the message, the kind of information the message conveys, and how to handle the message.</span></span> 
  
<span data-ttu-id="348e0-117">这些属性包含以句点串联的字符串。</span><span class="sxs-lookup"><span data-stu-id="348e0-117">These properties contain strings concatenated with periods.</span></span> <span data-ttu-id="348e0-118">每个字符串表示一个级别的子类。</span><span class="sxs-lookup"><span data-stu-id="348e0-118">Each string represents a level of subclassing.</span></span> <span data-ttu-id="348e0-119">例如, IPM。注释是 ipm 和 ipm 的超类的子类。注释。专用。</span><span class="sxs-lookup"><span data-stu-id="348e0-119">For example, IPM.Note is a subclass of IPM and a superclass of IPM.Note.Private.</span></span> 
  
<span data-ttu-id="348e0-120">这些属性必须由 ASCII 字符32到127组成, 并且不得以句点 (ASCII 46) 结尾。</span><span class="sxs-lookup"><span data-stu-id="348e0-120">These properties must consist of the ASCII characters 32 through 127 and must not end with a period (ASCII 46).</span></span> <span data-ttu-id="348e0-121">排序和比较操作必须将其视为不区分大小写的字符串。</span><span class="sxs-lookup"><span data-stu-id="348e0-121">Sort and compare operations must treat it as a case-insensitive string.</span></span> <span data-ttu-id="348e0-122">最大可能长度为255个字符, 但为了使 MAPI 会议室能够追加限定符, 建议将原长度保留在128个字符的下面。</span><span class="sxs-lookup"><span data-stu-id="348e0-122">The maximum possible length is 255 characters, but in order to allow MAPI room to append qualifiers it is recommended that the original length be kept under 128 characters.</span></span> 
  
<span data-ttu-id="348e0-123">需要提供这些属性的每封邮件。</span><span class="sxs-lookup"><span data-stu-id="348e0-123">Every message is required to furnish these properties.</span></span> <span data-ttu-id="348e0-124">通常情况下, 创建新邮件的客户端应用程序会在[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)成功返回后立即进行设置。</span><span class="sxs-lookup"><span data-stu-id="348e0-124">Normally, the client application creating a new message sets it as soon as [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) returns successfully.</span></span> <span data-ttu-id="348e0-125">但是, 如果客户端调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)时未设置该属性, 则邮件存储应将其设置为 IPM。</span><span class="sxs-lookup"><span data-stu-id="348e0-125">But if the property has not been set when the client calls [IMAPIProp::SaveChanges](imapiprop-savechanges.md), the message store should set it to IPM.</span></span> 
  
<span data-ttu-id="348e0-126">由 MAPI 定义的值为:</span><span class="sxs-lookup"><span data-stu-id="348e0-126">The values defined by MAPI are:</span></span> 
  
```cpp
IPM.Note for a standard interpersonal message 
REPORT.<subject message class>.DR for a delivery report 
REPORT.<subject message class>.NDR for a nondelivery report 
REPORT.<subject message class>.IPNRN for a read report 
REPORT.<subject message class>.IPNNRN for a nonread report 
 
```

<span data-ttu-id="348e0-127">IPM 和 IPC 仅适用于超类, 一条消息应至少追加一个子类限定符, 然后才能进行存储或提交。</span><span class="sxs-lookup"><span data-stu-id="348e0-127">IPM and IPC are intended to be superclasses only, and a message should have at least one subclass qualifier appended before being stored or submitted.</span></span> <span data-ttu-id="348e0-128">有关邮件类用法的详细信息, 请参阅[邮件类别](mapi-message-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="348e0-128">For more information on message class usage, see [Message Classes](mapi-message-classes.md).</span></span> <span data-ttu-id="348e0-129">有关邮件类别的必需属性和可选属性的列表, 请参阅[关于邮件属性](message-properties-overview.md)的副主题。</span><span class="sxs-lookup"><span data-stu-id="348e0-129">For lists of required and optional properties for message classes, see the subtopics of [About Message Properties](message-properties-overview.md).</span></span>
  
<span data-ttu-id="348e0-130">自定义邮件类可以在保留范围内定义仅与该邮件类一起使用的属性。</span><span class="sxs-lookup"><span data-stu-id="348e0-130">A custom message class can define properties in a reserved range for use with that message class only.</span></span> <span data-ttu-id="348e0-131">有关详细信息, 请参阅[关于属性标识符](mapi-property-identifier-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="348e0-131">For more information, see [About Property Identifiers](mapi-property-identifier-overview.md).</span></span> 
  
<span data-ttu-id="348e0-132">邮件类控制传入邮件存储在哪个接收文件夹中。</span><span class="sxs-lookup"><span data-stu-id="348e0-132">Message classes control which receive folder an incoming message is stored in.</span></span> <span data-ttu-id="348e0-133">有关详细信息, 请参阅[IMsgStore:: GetReceiveFolderTable](imsgstore-getreceivefoldertable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="348e0-133">For more information, see the [IMsgStore::GetReceiveFolderTable](imsgstore-getreceivefoldertable.md) method.</span></span> 
  
<span data-ttu-id="348e0-134">有关在窗体和窗体服务器中使用邮件类别的详细信息, 请参阅[选择邮件类别](choosing-a-message-class.md)。</span><span class="sxs-lookup"><span data-stu-id="348e0-134">For more information on using message classes with forms and form servers, see [Choosing a Message Class](choosing-a-message-class.md).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="348e0-135">相关资源</span><span class="sxs-lookup"><span data-stu-id="348e0-135">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="348e0-136">协议规范</span><span class="sxs-lookup"><span data-stu-id="348e0-136">Protocol specifications</span></span>

<span data-ttu-id="348e0-137">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="348e0-137">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="348e0-138">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="348e0-138">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="348e0-139">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="348e0-139">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="348e0-140">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="348e0-140">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="348e0-141">[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="348e0-141">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="348e0-142">指定允许用于电子邮件对象的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="348e0-142">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="348e0-143">[[毫秒-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="348e0-143">[[MS-OXOUM]](https://msdn.microsoft.com/library/2a0696c5-2caf-4f20-87fb-085db430afec%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="348e0-144">指定允许表示语音邮件和传真邮件的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="348e0-144">Specifies the properties and operations that are permissible for representing voice mail and fax messages.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="348e0-145">头文件</span><span class="sxs-lookup"><span data-stu-id="348e0-145">Header files</span></span>

<span data-ttu-id="348e0-146">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="348e0-146">Mapidefs.h</span></span>
  
> <span data-ttu-id="348e0-147">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="348e0-147">Provides data type definitions.</span></span>
    
<span data-ttu-id="348e0-148">Mapitags</span><span class="sxs-lookup"><span data-stu-id="348e0-148">Mapitags.h</span></span>
  
> <span data-ttu-id="348e0-149">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="348e0-149">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="348e0-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="348e0-150">See also</span></span>



[<span data-ttu-id="348e0-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="348e0-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="348e0-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="348e0-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="348e0-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="348e0-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="348e0-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="348e0-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

