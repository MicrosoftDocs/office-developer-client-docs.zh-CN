---
title: SetEOS 方法 (ADO)
TOCTitle: SetEOS method (ADO)
ms:assetid: d438eecf-7ab3-a07d-b6d5-8816db4aae7c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250063(v=office.15)
ms:contentKeyID: 48547933
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5f3b1ee81928a8da77cc3edff7f1feffb7196bba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308706"
---
# <a name="seteos-method-ado"></a>SetEOS 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于设置流的结束位置。

## <a name="syntax"></a>语法

*Stream*。SetEOS

## <a name="remarks"></a>注解

**SetEOS** 可通过将当前 [Position 属性 (ADO)](position-property-ado.md) 设为流末尾来更新 [EOS](eos-property-ado.md) 属性的值。当前位置后的任何字节或字符都将被截去。

由于 [Write](write-method-ado.md)、[WriteText](writetext-method-ado.md) 和 [CopyTo](copyto-method-ado.md) 不会截掉现有 **Stream** 对象中的任何额外值，因此可以通过用 **SetEOS** 设置新的流末尾位置来截去这些字节或字符。

> [!WARNING]
> 如果将 **EOS** 设置为实际流末尾之前的某个位置，则新的 **EOS** 位置后面的所有数据都将丢失。
