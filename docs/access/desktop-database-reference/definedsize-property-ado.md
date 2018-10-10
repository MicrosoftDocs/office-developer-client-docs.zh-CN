---
title: DefinedSize 属性 (ADO)
TOCTitle: DefinedSize Property (ADO)
ms:assetid: 8d6db4c9-fbdc-9fcd-63f0-bd677c5ebcf6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249619(v=office.15)
ms:contentKeyID: 48546257
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a8ffd8bb24abcab737ebc4bb23a0af717c02d486
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466092"
---
# <a name="definedsize-property-ado"></a><span data-ttu-id="3844e-102">DefinedSize 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3844e-102">DefinedSize Property (ADO)</span></span>


<span data-ttu-id="3844e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3844e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3844e-104">指示 [Field](field-object-ado.md) 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="3844e-104">Indicates the data capacity of a [Field](field-object-ado.md) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3844e-105">返回值</span><span class="sxs-lookup"><span data-stu-id="3844e-105">Return Value</span></span>

<span data-ttu-id="3844e-106">返回一个 **Long** 值，该值以字节数反映字段的定义大小。</span><span class="sxs-lookup"><span data-stu-id="3844e-106">Returns a **Long** value that reflects the defined size of a field as a number of bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="3844e-107">备注</span><span class="sxs-lookup"><span data-stu-id="3844e-107">Remarks</span></span>

<span data-ttu-id="3844e-108">使用 **DefinedSize** 属性可以确定 **Field** 对象的数据容量。</span><span class="sxs-lookup"><span data-stu-id="3844e-108">Use the **DefinedSize** property to determine the data capacity of a **Field** object.</span></span>

<span data-ttu-id="3844e-p101">**DefinedSize** 和 [ActualSize](actualsize-property-ado.md) 属性不同。例如，假如声明类型为 **adVarChar** 且 **DefinedSize** 属性值为 50 的 **Field** 对象中只包含了一个字符。其返回的 **ActualSize** 属性值为单个字符所占的字节长度。</span><span class="sxs-lookup"><span data-stu-id="3844e-p101">The **DefinedSize** and [ActualSize](actualsize-property-ado.md) properties are different. For example, consider a **Field** object with a declared type of **adVarChar** and a **DefinedSize** property value of 50, containing a single character. The **ActualSize** property value it returns is the length in bytes of the single character.</span></span>

