---
title: attMAPIProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 806270c1-30e4-494e-9b03-7d1f2fc04099
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 72f252791e374ed4b9b2a40c9b151ef2b91fefe6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588053"
---
# <a name="attmapiprops"></a><span data-ttu-id="8079e-103">attMAPIProps</span><span class="sxs-lookup"><span data-stu-id="8079e-103">attMAPIProps</span></span>

  
  
<span data-ttu-id="8079e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8079e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8079e-105">**AttMAPIProps**属性是特殊的这是的它可以用于对集合中的现有 TNEF 定义的属性没有对应的任何 MAPI 属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="8079e-105">The **attMAPIProps** attribute is special in that it can be used to encode any MAPI property that does not have a counterpart in the set of existing TNEF-defined attributes.</span></span> <span data-ttu-id="8079e-106">属性数据是一组计数排列的端到端的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="8079e-106">The attribute data is a counted set of MAPI properties laid end-to-end.</span></span> <span data-ttu-id="8079e-107">允许任何 MAPI 属性集合，其中的此编码，格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="8079e-107">The format of this encoding, which allows for any set of MAPI properties, is as follows:</span></span>  
  
 <span data-ttu-id="8079e-108">_Property_Seq:_</span><span class="sxs-lookup"><span data-stu-id="8079e-108">_Property_Seq:_</span></span>
  
> <span data-ttu-id="8079e-109">属性计数_Property_Value，..._</span><span class="sxs-lookup"><span data-stu-id="8079e-109">property-count  _Property_Value,..._</span></span>
    
<span data-ttu-id="8079e-110">必须尽可能多的_Property_Value_项目，如属性数值指示。</span><span class="sxs-lookup"><span data-stu-id="8079e-110">There must be as many  _Property_Value_ items as the property-count value indicates.</span></span> 
  
 <span data-ttu-id="8079e-111">_Property_Value:_</span><span class="sxs-lookup"><span data-stu-id="8079e-111">_Property_Value:_</span></span>
  
> <span data-ttu-id="8079e-112">属性标记 _Property_property tag _Proptag_Name 属性_</span><span class="sxs-lookup"><span data-stu-id="8079e-112">property-tag  _Property_property-tag  _Proptag_Name Property_</span></span>
    
<span data-ttu-id="8079e-113">属性标记就是属性标识符，如 0x0037001F **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 的相关联的值。</span><span class="sxs-lookup"><span data-stu-id="8079e-113">The property-tag is simply the value associated with the property identifier, such as 0x0037001F for **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)).</span></span>
  
 <span data-ttu-id="8079e-114">_属性：_</span><span class="sxs-lookup"><span data-stu-id="8079e-114">_Property:_</span></span>
  
>  <span data-ttu-id="8079e-115">_值_值计数_的值，..._</span><span class="sxs-lookup"><span data-stu-id="8079e-115">_Value_ value-count  _Value,..._</span></span>
    
 <span data-ttu-id="8079e-116">_值：_</span><span class="sxs-lookup"><span data-stu-id="8079e-116">_Value:_</span></span>
  
> <span data-ttu-id="8079e-117">数值数据值大小值的数据填充值大小值 IID 数值数据填充</span><span class="sxs-lookup"><span data-stu-id="8079e-117">value-data value-size value-data padding value-size value-IID value-data padding</span></span>
    
 <span data-ttu-id="8079e-118">_Proptag_Name:_</span><span class="sxs-lookup"><span data-stu-id="8079e-118">_Proptag_Name:_</span></span>
  
> <span data-ttu-id="8079e-119">名称 guid 名称类型名称 id 名称-guid 名称类型名称字符串长度名称字符串填充</span><span class="sxs-lookup"><span data-stu-id="8079e-119">name-guid name-kind name-id name-guid name-kind name-string-length name-string padding</span></span>
    
<span data-ttu-id="8079e-120">每个属性封装异属性标识符和属性类型。</span><span class="sxs-lookup"><span data-stu-id="8079e-120">The encapsulation of each property varies based on the property identifier and the property type.</span></span> <span data-ttu-id="8079e-121">Mapitags.h 和 Mapidefs.h 头文件中定义属性标记、 标识符和类型。</span><span class="sxs-lookup"><span data-stu-id="8079e-121">Property tags, identifiers, and types are defined in the Mapitags.h and Mapidefs.h header files.</span></span>
  
<span data-ttu-id="8079e-122">如果该属性是命名的属性，然后属性标记紧跟组成的全局唯一标识符 (GUID)、 类型和标识符或 Unicode 字符串的 MAPI 属性名称。</span><span class="sxs-lookup"><span data-stu-id="8079e-122">If the property is a named property, then the property tag is immediately followed by the MAPI property name, consisting of a globally unique identifier (GUID), a type, and either an identifier or a Unicode string.</span></span>
  
<span data-ttu-id="8079e-123">多值的属性和具有可变长度值属性，如 PT_BINARY、 PT_STRING8、 PT_UNICODE 或 PT_OBJECT 属性类型，按以下方式处理。</span><span class="sxs-lookup"><span data-stu-id="8079e-123">Multivalued properties and properties with variable length values, such as the PT_BINARY, PT_STRING8, PT_UNICODE, or PT_OBJECT property types, are treated in the following way.</span></span> <span data-ttu-id="8079e-124">首先数量的值，编码为 32 位无符号长，位于在 TNEF 流中后, 跟的单个值。</span><span class="sxs-lookup"><span data-stu-id="8079e-124">First the number of values, encoded as a 32-bit unsigned long, is placed in the TNEF stream, followed by the individual values.</span></span> <span data-ttu-id="8079e-125">每个属性值的数据被编码为以字节为单位的值数据本身后跟尺寸。</span><span class="sxs-lookup"><span data-stu-id="8079e-125">Each property's value-data is encoded as its size in bytes followed by the value-data itself.</span></span> <span data-ttu-id="8079e-126">数值数据被填充为 4 字节，尽管的填充量不包含值大小。</span><span class="sxs-lookup"><span data-stu-id="8079e-126">The value-data is padded out to a 4-byte boundary, although the amount of padding is not included in the value-size.</span></span>
  
<span data-ttu-id="8079e-127">如果该属性的类型 PT_OBJECT，值大小后跟对象的界面标识符。</span><span class="sxs-lookup"><span data-stu-id="8079e-127">If the property is of type PT_OBJECT, the value-size is followed by the interface identifier of the object.</span></span> <span data-ttu-id="8079e-128">TNEF 的当前实现仅支持 IID_IMessage、 IID_IStorage 和 IID_Istream 界面标识符。</span><span class="sxs-lookup"><span data-stu-id="8079e-128">The current implementation of TNEF only supports the IID_IMessage, IID_IStorage, and IID_Istream interface identifiers.</span></span> <span data-ttu-id="8079e-129">包含值大小接口标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="8079e-129">The size of the interface identifier is included in the value-size.</span></span>
  
<span data-ttu-id="8079e-130">如果对象是嵌入的邮件 （即，它具有 PT_OBJECT 和 IID_Imessage 接口标识符的属性类型，） 的值数据编码为嵌入的 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="8079e-130">If the object is an embedded message (that is, it has a property type of PT_OBJECT and an interface identifier of IID_Imessage), the value data is encoded as an embedded TNEF stream.</span></span> <span data-ttu-id="8079e-131">邮件嵌入 TNEF 实现中的实际编码是通过打开的原始流的第二个 TNEF 对象和处理流内嵌。</span><span class="sxs-lookup"><span data-stu-id="8079e-131">The actual encoding of an embedded message in TNEF implementation is done by opening a second TNEF object for the original stream and processing the stream inline.</span></span>
  

