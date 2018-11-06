---
title: Position 属性 (ADO)
TOCTitle: Position property (ADO)
ms:assetid: a07c9197-673b-ddf2-fca9-b0b54fbd67b4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249738(v=office.15)
ms:contentKeyID: 48546709
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0d4d907cedc3490f4ca13d47a12b9719cf3e2ee1
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997152"
---
# <a name="position-property-ado"></a>Position 属性 (ADO)

**适用于**： Access 2013、 Office 2013

指示 [Stream](stream-object-ado.md) 对象中的当前位置。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指定当前位置从流开始处的偏移量（以字节为单位）。默认值为 0，表示流中的第一个字节。

## <a name="remarks"></a>备注

当前位置可移至流末尾之后的某点。如果在流末尾之后指定当前位置，则 [Stream](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/size-property-ado-stream) 对象的 **Size** 也将相应增加。按这种方法添加的任何新字节均将为空。

> [!NOTE]
> [!注释] **Position** 始终以字节为单位。对于使用多字节字符集的文本流，将位置值乘以字符大小可确定字符编号。例如，对于双字节字符集，第一个字符处于位置 0，第二个字符处于位置 2，第三个字符处于位置 4，依此类推。

不能使用负值更改 **Stream** 中的当前位置。只有整数可用于 **Position** 。

对于只读 **Stream** 对象，如果将 **Position** 设置为大于 **Stream** 的 **Size** 的值，则 ADO 不会返回错误。这样并不会更改 **Stream** 的大小，也不会以任何方式改变 **Stream** 的内容。但是，由于会导致无意义的 **Position** 值，因此应避免这样做。

