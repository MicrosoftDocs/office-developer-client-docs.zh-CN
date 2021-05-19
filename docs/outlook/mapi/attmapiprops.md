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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410453"
---
# <a name="attmapiprops"></a><span data-ttu-id="ca90c-103">attMAPIProps</span><span class="sxs-lookup"><span data-stu-id="ca90c-103">attMAPIProps</span></span>

  
  
<span data-ttu-id="ca90c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca90c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca90c-105">**attMAPIProps** 属性很特殊，可用于对现有的 TNEF 定义属性集内没有对应属性的任何 MAPI 属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="ca90c-105">The **attMAPIProps** attribute is special in that it can be used to encode any MAPI property that does not have a counterpart in the set of existing TNEF-defined attributes.</span></span> <span data-ttu-id="ca90c-106">属性数据是一组端到端布置的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ca90c-106">The attribute data is a counted set of MAPI properties laid end-to-end.</span></span> <span data-ttu-id="ca90c-107">此编码的格式允许任意一组 MAPI 属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca90c-107">The format of this encoding, which allows for any set of MAPI properties, is as follows:</span></span>  
  
 <span data-ttu-id="ca90c-108">_Property_Seq：_</span><span class="sxs-lookup"><span data-stu-id="ca90c-108">_Property_Seq:_</span></span>
  
> <span data-ttu-id="ca90c-109">属性计数  _Property_Value,..._</span><span class="sxs-lookup"><span data-stu-id="ca90c-109">property-count  _Property_Value,..._</span></span>
    
<span data-ttu-id="ca90c-110">必须存在与属性  _Property_Value_ 值指示的项数一样多。</span><span class="sxs-lookup"><span data-stu-id="ca90c-110">There must be as many  _Property_Value_ items as the property-count value indicates.</span></span> 
  
 <span data-ttu-id="ca90c-111">_Property_Value：_</span><span class="sxs-lookup"><span data-stu-id="ca90c-111">_Property_Value:_</span></span>
  
> <span data-ttu-id="ca90c-112">property-tag _Property_property-tag  _Proptag_Name Property_</span><span class="sxs-lookup"><span data-stu-id="ca90c-112">property-tag  _Property_property-tag  _Proptag_Name Property_</span></span>
    
<span data-ttu-id="ca90c-113">property-tag 只是与属性标识符关联的值，例如 0x0037001F **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="ca90c-113">The property-tag is simply the value associated with the property identifier, such as 0x0037001F for **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)).</span></span>
  
 <span data-ttu-id="ca90c-114">_属性：_</span><span class="sxs-lookup"><span data-stu-id="ca90c-114">_Property:_</span></span>
  
>  <span data-ttu-id="ca90c-115">_值_ 值计数  _值,..._</span><span class="sxs-lookup"><span data-stu-id="ca90c-115">_Value_ value-count  _Value,..._</span></span>
    
 <span data-ttu-id="ca90c-116">_值：_</span><span class="sxs-lookup"><span data-stu-id="ca90c-116">_Value:_</span></span>
  
> <span data-ttu-id="ca90c-117">value-data value-size value-data padding value-size value-IID value-data padding</span><span class="sxs-lookup"><span data-stu-id="ca90c-117">value-data value-size value-data padding value-size value-IID value-data padding</span></span>
    
 <span data-ttu-id="ca90c-118">_Proptag_Name：_</span><span class="sxs-lookup"><span data-stu-id="ca90c-118">_Proptag_Name:_</span></span>
  
> <span data-ttu-id="ca90c-119">name-guid name-kind name-id name-guid name-kind name-string-length name-string padding</span><span class="sxs-lookup"><span data-stu-id="ca90c-119">name-guid name-kind name-id name-guid name-kind name-string-length name-string padding</span></span>
    
<span data-ttu-id="ca90c-120">每个属性的封装因属性标识符和属性类型而异。</span><span class="sxs-lookup"><span data-stu-id="ca90c-120">The encapsulation of each property varies based on the property identifier and the property type.</span></span> <span data-ttu-id="ca90c-121">属性标记、标识符和类型在 Mapitags.h 和 Mapidefs.h 头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="ca90c-121">Property tags, identifiers, and types are defined in the Mapitags.h and Mapidefs.h header files.</span></span>
  
<span data-ttu-id="ca90c-122">如果该属性是命名属性，则属性标记后紧跟 MAPI 属性名称，由全局唯一标识符 (GUID) 、类型以及标识符或 Unicode 字符串组成。</span><span class="sxs-lookup"><span data-stu-id="ca90c-122">If the property is a named property, then the property tag is immediately followed by the MAPI property name, consisting of a globally unique identifier (GUID), a type, and either an identifier or a Unicode string.</span></span>
  
<span data-ttu-id="ca90c-123">使用可变长度值（如 PT_BINARY、PT_STRING8、PT_UNICODE 或 PT_OBJECT 属性类型）的多值属性和属性将按以下方式处理。</span><span class="sxs-lookup"><span data-stu-id="ca90c-123">Multivalued properties and properties with variable length values, such as the PT_BINARY, PT_STRING8, PT_UNICODE, or PT_OBJECT property types, are treated in the following way.</span></span> <span data-ttu-id="ca90c-124">首先，编码为 32 位无符号长的值数放置在 TNEF 流中，后跟各个值。</span><span class="sxs-lookup"><span data-stu-id="ca90c-124">First the number of values, encoded as a 32-bit unsigned long, is placed in the TNEF stream, followed by the individual values.</span></span> <span data-ttu-id="ca90c-125">每个属性的值数据都编码为大小（以字节为单位）后跟值数据本身。</span><span class="sxs-lookup"><span data-stu-id="ca90c-125">Each property's value-data is encoded as its size in bytes followed by the value-data itself.</span></span> <span data-ttu-id="ca90c-126">尽管值大小中不包含填充量，但值数据将填充到 4 字节边界。</span><span class="sxs-lookup"><span data-stu-id="ca90c-126">The value-data is padded out to a 4-byte boundary, although the amount of padding is not included in the value-size.</span></span>
  
<span data-ttu-id="ca90c-127">如果属性的类型为 PT_OBJECT，则值大小后跟对象的接口标识符。</span><span class="sxs-lookup"><span data-stu-id="ca90c-127">If the property is of type PT_OBJECT, the value-size is followed by the interface identifier of the object.</span></span> <span data-ttu-id="ca90c-128">TNEF 的当前实现仅支持IID_IMessage、IID_IStorage和IID_Istream标识符。</span><span class="sxs-lookup"><span data-stu-id="ca90c-128">The current implementation of TNEF only supports the IID_IMessage, IID_IStorage, and IID_Istream interface identifiers.</span></span> <span data-ttu-id="ca90c-129">接口标识符的大小包含在值大小中。</span><span class="sxs-lookup"><span data-stu-id="ca90c-129">The size of the interface identifier is included in the value-size.</span></span>
  
<span data-ttu-id="ca90c-130">如果对象是嵌入 (，即其属性类型为 PT_OBJECT 且接口标识符为 IID_Imessage) ，则值数据将编码为嵌入的 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="ca90c-130">If the object is an embedded message (that is, it has a property type of PT_OBJECT and an interface identifier of IID_Imessage), the value data is encoded as an embedded TNEF stream.</span></span> <span data-ttu-id="ca90c-131">在 TNEF 实现中，嵌入邮件的实际编码通过为原始流打开第二个 TNEF 对象并内联处理流完成。</span><span class="sxs-lookup"><span data-stu-id="ca90c-131">The actual encoding of an embedded message in TNEF implementation is done by opening a second TNEF object for the original stream and processing the stream inline.</span></span>
  

