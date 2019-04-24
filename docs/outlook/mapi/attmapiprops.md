---
title: attMAPIProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 806270c1-30e4-494e-9b03-7d1f2fc04099
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 185bfbb151c4f8d4e36b40b94393d14d50c33edf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318121"
---
# <a name="attmapiprops"></a><span data-ttu-id="19978-103">attMAPIProps</span><span class="sxs-lookup"><span data-stu-id="19978-103">attMAPIProps</span></span>

  
  
<span data-ttu-id="19978-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19978-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19978-105">**attMAPIProps**属性是特别的, 因为它可用于对在现有 TNEF 定义的属性集中没有对应属性的任何 MAPI 属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="19978-105">The **attMAPIProps** attribute is special in that it can be used to encode any MAPI property that does not have a counterpart in the set of existing TNEF-defined attributes.</span></span> <span data-ttu-id="19978-106">属性数据是按端到端排列的一组已计数的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="19978-106">The attribute data is a counted set of MAPI properties laid end-to-end.</span></span> <span data-ttu-id="19978-107">此编码的格式 (允许任何 MAPI 属性集) 如下所示:</span><span class="sxs-lookup"><span data-stu-id="19978-107">The format of this encoding, which allows for any set of MAPI properties, is as follows:</span></span>  
  
 <span data-ttu-id="19978-108">_Property_Seq:_</span><span class="sxs-lookup"><span data-stu-id="19978-108">_Property_Seq:_</span></span>
  
> <span data-ttu-id="19978-109">属性计数_Property_Value,..._</span><span class="sxs-lookup"><span data-stu-id="19978-109">property-count  _Property_Value,..._</span></span>
    
<span data-ttu-id="19978-110">必须有与属性-count 值指示的_Property_Value_项目数。</span><span class="sxs-lookup"><span data-stu-id="19978-110">There must be as many  _Property_Value_ items as the property-count value indicates.</span></span> 
  
 <span data-ttu-id="19978-111">_Property_Value:_</span><span class="sxs-lookup"><span data-stu-id="19978-111">_Property_Value:_</span></span>
  
> <span data-ttu-id="19978-112">属性标记 _Property_property-tag _Proptag_Name 属性_</span><span class="sxs-lookup"><span data-stu-id="19978-112">property-tag  _Property_property-tag  _Proptag_Name Property_</span></span>
    
<span data-ttu-id="19978-113">属性标记只是与属性标识符关联的值, 如 0x0037001F for **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="19978-113">The property-tag is simply the value associated with the property identifier, such as 0x0037001F for **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)).</span></span>
  
 <span data-ttu-id="19978-114">_财产_</span><span class="sxs-lookup"><span data-stu-id="19978-114">_Property:_</span></span>
  
>  <span data-ttu-id="19978-115">_值_值-计数_值,..._</span><span class="sxs-lookup"><span data-stu-id="19978-115">_Value_ value-count  _Value,..._</span></span>
    
 <span data-ttu-id="19978-116">_值：_</span><span class="sxs-lookup"><span data-stu-id="19978-116">_Value:_</span></span>
  
> <span data-ttu-id="19978-117">值-数据值大小值-数据填充值-IID 值-数据填充</span><span class="sxs-lookup"><span data-stu-id="19978-117">value-data value-size value-data padding value-size value-IID value-data padding</span></span>
    
 <span data-ttu-id="19978-118">_Proptag_Name:_</span><span class="sxs-lookup"><span data-stu-id="19978-118">_Proptag_Name:_</span></span>
  
> <span data-ttu-id="19978-119">name-guid 名称-种类名称-id name-guid 名称-种类名称-字符串长度名称-字符串填充</span><span class="sxs-lookup"><span data-stu-id="19978-119">name-guid name-kind name-id name-guid name-kind name-string-length name-string padding</span></span>
    
<span data-ttu-id="19978-120">每个属性的封装根据属性标识符和属性类型的不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="19978-120">The encapsulation of each property varies based on the property identifier and the property type.</span></span> <span data-ttu-id="19978-121">属性标记、标识符和类型是在 Mapitags 和 mapidefs.h 头文件中定义的。</span><span class="sxs-lookup"><span data-stu-id="19978-121">Property tags, identifiers, and types are defined in the Mapitags.h and Mapidefs.h header files.</span></span>
  
<span data-ttu-id="19978-122">如果属性为命名的属性, 则该属性标记后紧跟 MAPI 属性名称, 由全局唯一标识符 (GUID)、类型以及标识符或 Unicode 字符串组成。</span><span class="sxs-lookup"><span data-stu-id="19978-122">If the property is a named property, then the property tag is immediately followed by the MAPI property name, consisting of a globally unique identifier (GUID), a type, and either an identifier or a Unicode string.</span></span>
  
<span data-ttu-id="19978-123">多值属性和具有可变长度值的属性 (如 PT_BINARY、PT_STRING8、PT_UNICODE 或 PT_OBJECT 属性类型) 按以下方式处理。</span><span class="sxs-lookup"><span data-stu-id="19978-123">Multivalued properties and properties with variable length values, such as the PT_BINARY, PT_STRING8, PT_UNICODE, or PT_OBJECT property types, are treated in the following way.</span></span> <span data-ttu-id="19978-124">首先, 将编码为32位无符号长的值的数目放在 TNEF 流中, 后跟各个值。</span><span class="sxs-lookup"><span data-stu-id="19978-124">First the number of values, encoded as a 32-bit unsigned long, is placed in the TNEF stream, followed by the individual values.</span></span> <span data-ttu-id="19978-125">每个属性的值数据都以字节为单位的大小, 后跟值数据本身。</span><span class="sxs-lookup"><span data-stu-id="19978-125">Each property's value-data is encoded as its size in bytes followed by the value-data itself.</span></span> <span data-ttu-id="19978-126">将值数据填充到4字节边界, 尽管填充量不包含在 value-size 中。</span><span class="sxs-lookup"><span data-stu-id="19978-126">The value-data is padded out to a 4-byte boundary, although the amount of padding is not included in the value-size.</span></span>
  
<span data-ttu-id="19978-127">如果属性的类型为 PT_OBJECT, 则值大小后跟对象的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="19978-127">If the property is of type PT_OBJECT, the value-size is followed by the interface identifier of the object.</span></span> <span data-ttu-id="19978-128">当前的 TNEF 实现仅支持 IID_IMessage、IID_IStorage 和 IID_Istream 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="19978-128">The current implementation of TNEF only supports the IID_IMessage, IID_IStorage, and IID_Istream interface identifiers.</span></span> <span data-ttu-id="19978-129">接口标识符的大小包含在值大小中。</span><span class="sxs-lookup"><span data-stu-id="19978-129">The size of the interface identifier is included in the value-size.</span></span>
  
<span data-ttu-id="19978-130">如果对象是嵌入的邮件 (即, 它的属性类型为 PT_OBJECT, 接口标识符为 IID_Imessage), 则将值数据编码为嵌入的 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="19978-130">If the object is an embedded message (that is, it has a property type of PT_OBJECT and an interface identifier of IID_Imessage), the value data is encoded as an embedded TNEF stream.</span></span> <span data-ttu-id="19978-131">通过打开原始流的第二个 TNEF 对象并以内嵌方式处理流, 可以完成 TNEF 实现中嵌入邮件的实际编码。</span><span class="sxs-lookup"><span data-stu-id="19978-131">The actual encoding of an embedded message in TNEF implementation is done by opening a second TNEF object for the original stream and processing the stream inline.</span></span>
  

