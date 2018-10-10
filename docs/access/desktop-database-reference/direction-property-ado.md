---
title: Direction 属性 (ADO)
TOCTitle: Direction Property (ADO)
ms:assetid: 51a94abb-7ce9-9adb-2b76-5391eb9f6863
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249262(v=office.15)
ms:contentKeyID: 48544823
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 611e5efbe53964c5ba255380e2659f024bd6be9a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467500"
---
# <a name="direction-property-ado"></a>Direction 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示 [Parameter](parameter-object-ado.md) 参数是表示输入参数、输出参数还是输入输出参数，或者该参数是否为某个存储过程的返回值。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回 [ParameterDirectionEnum](parameterdirectionenum.md) 值。

## <a name="remarks"></a>备注

使用 **Direction** 属性可以指定如何向过程或从过程传递参数。 **Direction** 属性为读/写属性；这样就可以使用不会返回此信息的提供程序，或者在不希望 ADO 对提供程序进行额外调用来检索参数信息的情况下设置此信息。

并非所有提供程序都可以确定其存储过程中的参数传递方向。在这种情况下，必须在执行查询前设置 **Direction** 属性。

