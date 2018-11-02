---
title: SetEOS 方法 (ADO)
TOCTitle: SetEOS method (ADO)
ms:assetid: d438eecf-7ab3-a07d-b6d5-8816db4aae7c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250063(v=office.15)
ms:contentKeyID: 48547933
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8eda32f026c0fb706f15da3760c3dba879aae9d6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25928321"
---
# <a name="seteos-method-ado"></a><span data-ttu-id="7deec-102">SetEOS 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7deec-102">SetEOS method (ADO)</span></span>


<span data-ttu-id="7deec-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7deec-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7deec-104">用于设置流的结束位置。</span><span class="sxs-lookup"><span data-stu-id="7deec-104">Sets the position that is the end of the stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="7deec-105">语法</span><span class="sxs-lookup"><span data-stu-id="7deec-105">Syntax</span></span>

<span data-ttu-id="7deec-106">*流*。SetEOS</span><span class="sxs-lookup"><span data-stu-id="7deec-106">*Stream*.SetEOS</span></span>

## <a name="remarks"></a><span data-ttu-id="7deec-107">备注</span><span class="sxs-lookup"><span data-stu-id="7deec-107">Remarks</span></span>

<span data-ttu-id="7deec-p101">**SetEOS** 可通过将当前 [Position 属性 (ADO)](eos-property-ado.md) 设为流末尾来更新 [EOS](position-property-ado.md) 属性的值。当前位置后的任何字节或字符都将被截去。</span><span class="sxs-lookup"><span data-stu-id="7deec-p101">**SetEOS** updates the value of the [EOS](eos-property-ado.md) property, by making the current [Position](position-property-ado.md) the end of the stream. Any bytes or characters following the current position are truncated.</span></span>

<span data-ttu-id="7deec-110">由于 [Write](write-method-ado.md)、[WriteText](writetext-method-ado.md) 和 [CopyTo](copyto-method-ado.md) 不会截掉现有 **Stream** 对象中的任何额外值，因此可以通过用 **SetEOS** 设置新的流末尾位置来截去这些字节或字符。</span><span class="sxs-lookup"><span data-stu-id="7deec-110">Since [Write](write-method-ado.md), [WriteText](writetext-method-ado.md), and [CopyTo](copyto-method-ado.md) do not truncate any extra values in existing **Stream** objects, you can truncate these bytes or characters by setting the new end-of-stream position with **SetEOS**.</span></span>


> [!WARNING]
> <P><span data-ttu-id="7deec-111">如果将 <STRONG>EOS</STRONG> 设置为实际流末尾之前的某个位置，则新的 <STRONG>EOS</STRONG> 位置后面的所有数据都将丢失。</span><span class="sxs-lookup"><span data-stu-id="7deec-111">If you set <STRONG>EOS</STRONG> to a position before the actual end of the stream, you will lose all data after the new <STRONG>EOS</STRONG> position.</span></span></P>


