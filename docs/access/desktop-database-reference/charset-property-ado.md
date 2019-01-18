---
title: Charset 属性 (ADO)
TOCTitle: Charset property (ADO)
ms:assetid: 454f664e-6d62-eec9-487d-882c2f9503b0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249213(v=office.15)
ms:contentKeyID: 48544551
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ca4640940c217fd81cac4ba1d8ffaf769b506fe0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703977"
---
# <a name="charset-property-ado"></a>Charset 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示一个字符集，文本 [Stream](stream-object-ado.md) 的内容应转换为该字符集，以存储在 Stream 对象内部缓冲区中。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **String** 值，该值指定 **Stream** 的内容将要转换为的字符集。 默认值为"Unicode"。 允许的值为作为 Internet 字符集字符串通过接口传递的常见字符串（例如，"iso-8859-1"、"Windows-1252"等）。 由系统已知的字符串集列表，请参阅 HKEY 的子项\_类\_根\\MIME\\数据库\\Windows 注册表中的字符集。

## <a name="remarks"></a>备注

在文本 **Stream** 对象中，文本数据是采用 **Charset** 属性指定的字符集存储的。默认值为"Unicode"。 **Charset** 属性用于对传入 **Stream** 或从 **Stream** 传出的数据进行转换。例如，如果 **Stream** 包含 ISO-8859-1 数据，而又要将该数据复制到 BSTR 中， **Stream** 对象会将该数据转换为 Unicode。反之亦然。

对于打开的 **Stream** ，当前的 [Position](position-property-ado.md) 值必须位于 **Stream** 的开始处 (0)，才能设置 **Charset** 。

**Charset** 仅与文本 **Stream** 对象（[Type](type-property-ado-stream.md) 为 **adTypeText**）一起使用。如果 **Type** 为 **adTypeBinary**，则忽略此属性。

