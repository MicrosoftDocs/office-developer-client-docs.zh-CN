---
title: Position 属性 (ADO)
TOCTitle: Position property (ADO)
ms:assetid: a07c9197-673b-ddf2-fca9-b0b54fbd67b4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249738(v=office.15)
ms:contentKeyID: 48546709
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ab1111cdbc0e5a319f1f3431477854c6d38eff20
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875404"
---
# <a name="position-property-ado"></a>Position 属性 (ADO)


**适用于**： Access 2013、 Office 2013

指示 [Stream](stream-object-ado.md) 对象中的当前位置。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Long** 值，指定当前位置从流开始处的偏移量（以字节为单位）。默认值为 0，表示流中的第一个字节。

## <a name="remarks"></a>备注

当前位置可移至流末尾之后的某点。如果在流末尾之后指定当前位置，则 [Stream](https://msdn.microsoft.com/library/jj250128\(v=office.15\)) 对象的 **Size** 也将相应增加。按这种方法添加的任何新字节均将为空。


> [!NOTE]
> <P>[!注释] <STRONG>Position</STRONG> 始终以字节为单位。对于使用多字节字符集的文本流，将位置值乘以字符大小可确定字符编号。例如，对于双字节字符集，第一个字符处于位置 0，第二个字符处于位置 2，第三个字符处于位置 4，依此类推。</P>



不能使用负值更改 **Stream** 中的当前位置。只有整数可用于 **Position** 。

对于只读 **Stream** 对象，如果将 **Position** 设置为大于 **Stream** 的 **Size** 的值，则 ADO 不会返回错误。这样并不会更改 **Stream** 的大小，也不会以任何方式改变 **Stream** 的内容。但是，由于会导致无意义的 **Position** 值，因此应避免这样做。

