---
title: Size 属性 (ADO)
TOCTitle: Size Property (ADO)
ms:assetid: 24596b5c-b1cc-e97e-68b6-8ff53baf150b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249017(v=office.15)
ms:contentKeyID: 48543753
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6b690bd735f01e077b52c13c6c6e9b478234c1e8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468321"
---
# <a name="size-property-ado"></a><span data-ttu-id="03a68-102">Size 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="03a68-102">Size Property (ADO)</span></span>


<span data-ttu-id="03a68-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="03a68-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="03a68-104">指示 [Parameter](parameter-object-ado.md) 对象的最大大小，以字节或字符为单位。</span><span class="sxs-lookup"><span data-stu-id="03a68-104">Indicates the maximum size, in bytes or characters, of a [Parameter](parameter-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="03a68-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="03a68-105">Settings and Return Values</span></span>

<span data-ttu-id="03a68-106">设置或返回一个指示 **Parameter** 对象最大大小的 **Long** 值，以字节或字符为单位。</span><span class="sxs-lookup"><span data-stu-id="03a68-106">Sets or returns a **Long** value that indicates the maximum size in bytes or characters of a value in a **Parameter** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="03a68-107">备注</span><span class="sxs-lookup"><span data-stu-id="03a68-107">Remarks</span></span>

<span data-ttu-id="03a68-108">使用 **Size** 属性可确定写入 [Parameter](value-property-ado.md) 对象的 **Value** 属性或从中读取的值的最大大小。</span><span class="sxs-lookup"><span data-stu-id="03a68-108">Use the **Size** property to determine the maximum size for values written to or read from the [Value](value-property-ado.md) property of a **Parameter** object.</span></span>

<span data-ttu-id="03a68-109">如果要指定 **Parameter** 对象为可变长度数据类型（例如，任何 **String** 类型，如 **adVarChar**），则必须先设置对象的 **Size** 属性，然后再将该对象追加到 [Parameters](parameters-collection-ado.md) 集合；否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="03a68-109">If you specify a variable-length data type for a **Parameter** object (for example, any **String** type, such as **adVarChar**), you must set the object's **Size** property before appending it to the [Parameters](parameters-collection-ado.md) collection; otherwise, an error occurs.</span></span>

<span data-ttu-id="03a68-110">如果已经将 **Parameter** 对象追加到 **Command** 对象的 [Parameters](command-object-ado.md) 集合，并已经将它的类型更改为可变长度数据类型，那么必须先设置 **Parameter** 对象的 **Size** 属性，然后再执行 **Command** 对象；否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="03a68-110">If you have already appended the **Parameter** object to the **Parameters** collection of a [Command](command-object-ado.md) object and you change its type to a variable-length data type, you must set the **Parameter** object's **Size** property before executing the **Command** object; otherwise, an error occurs.</span></span>

<span data-ttu-id="03a68-p101">如果使用 [Refresh](refresh-method-ado.md) 方法从提供程序获取参数信息，并且提供程序返回一个或多个可变长度数据类型的 **Parameter** 对象，则 ADO 可能会根据其最大可能大小为其分配内存空间，这样在执行过程中可能会导致错误。为避免出错，应该在执行命令之前显式设置这些参数的 **Size** 属性。</span><span class="sxs-lookup"><span data-stu-id="03a68-p101">If you use the [Refresh](refresh-method-ado.md) method to obtain parameter information from the provider and it returns one or more variable-length data type **Parameter** objects, ADO may allocate memory for the parameters based on their maximum potential size, which could cause an error during execution. To prevent an error, you should explicitly set the **Size** property for these parameters before executing the command.</span></span>

<span data-ttu-id="03a68-113">**Size** 为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="03a68-113">The **Size** property is read/write.</span></span>

