---
title: SetEOS 方法 (ADO)
TOCTitle: SetEOS Method (ADO)
ms:assetid: d438eecf-7ab3-a07d-b6d5-8816db4aae7c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250063(v=office.15)
ms:contentKeyID: 48547933
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 420d614d100ed156b794e92f77df2e7a4180c9fb
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872429"
---
# <a name="seteos-method-ado"></a>SetEOS 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于设置流的结束位置。

## <a name="syntax"></a>语法

*流*。SetEOS

## <a name="remarks"></a>备注

**SetEOS** 可通过将当前 [Position 属性 (ADO)](eos-property-ado.md) 设为流末尾来更新 [EOS](position-property-ado.md) 属性的值。当前位置后的任何字节或字符都将被截去。

由于 [Write](write-method-ado.md)、[WriteText](writetext-method-ado.md) 和 [CopyTo](copyto-method-ado.md) 不会截掉现有 **Stream** 对象中的任何额外值，因此可以通过用 **SetEOS** 设置新的流末尾位置来截去这些字节或字符。


> [!WARNING]
> <P>如果将 <STRONG>EOS</STRONG> 设置为实际流末尾之前的某个位置，则新的 <STRONG>EOS</STRONG> 位置后面的所有数据都将丢失。</P>


