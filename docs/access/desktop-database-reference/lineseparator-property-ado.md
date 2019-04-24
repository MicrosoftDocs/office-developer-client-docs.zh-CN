---
title: LineSeparator 属性 (ADO)
TOCTitle: LineSeparator property (ADO)
ms:assetid: 9f1323cd-d4ed-2bfa-554b-faebab529548
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249729(v=office.15)
ms:contentKeyID: 48546676
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4e941339ad1c8622d1c87ada848a44fa82a9ef2d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289947"
---
# <a name="lineseparator-property-ado"></a>LineSeparator 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示要在文本 [Stream](stream-object-ado.md) 对象中用作行分隔符的二进制字符。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 [LineSeparatorsEnum](lineseparatorsenum.md) 值，指示在 **Stream** 中使用的分行符。 默认值为 **adCRLF**。

## <a name="remarks"></a>注解

**LineSeparator** 用于在读取文本 **Stream** 的内容时解释行。可通过 [SkipLine](skipline-method-ado.md) 方法进行跳行。

**LineSeparator** 仅用于文本 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**）。 如果 **Type** 为 **adTypeBinary**，则忽略此属性。

