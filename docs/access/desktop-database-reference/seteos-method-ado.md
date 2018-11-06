---
title: SetEOS 方法 (ADO)
TOCTitle: SetEOS method (ADO)
ms:assetid: d438eecf-7ab3-a07d-b6d5-8816db4aae7c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250063(v=office.15)
ms:contentKeyID: 48547933
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b45e716844b3e616dfe5b8f94d69f29d6b0f1042
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997509"
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
> 如果将 **EOS** 设置为实际流末尾之前的某个位置，则新的 **EOS** 位置后面的所有数据都将丢失。