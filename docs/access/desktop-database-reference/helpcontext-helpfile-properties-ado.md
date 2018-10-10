---
title: HelpContext、HelpFile 属性 (ADO)
TOCTitle: HelpContext, HelpFile Properties (ADO)
ms:assetid: 8a79f994-f17c-2983-0593-095801be762e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249608(v=office.15)
ms:contentKeyID: 48546194
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 23823ec18b4b87306fa852ac5b0b18e89f60d057
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468208"
---
# <a name="helpcontext-helpfile-properties-ado"></a>HelpContext、HelpFile 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示与 [Error](error-object-ado.md) 对象关联的帮助文件和主题。

## <a name="return-values"></a>返回值

  - **HelpContextID**  返回帮助文件中主题的上下文 ID，返回值的类型为 **Long** 。

  - **HelpFile**  返回一个 **String** 类型的值，作为帮助文件完全解析路径的计算结果。

## <a name="remarks"></a>备注

如果在 **HelpFile** 属性中指定了帮助文件，则 **HelpContext** 属性用于自动显示其标识的帮助主题。如果没有相关的帮助主题可用，则 **HelpContext** 属性返回 0，并且 **HelpFile** 属性返回一个零长度字符串 ("")。

