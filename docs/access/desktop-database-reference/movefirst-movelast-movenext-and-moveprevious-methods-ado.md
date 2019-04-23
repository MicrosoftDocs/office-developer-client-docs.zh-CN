---
title: MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (ADO)
TOCTitle: MoveFirst, MoveLast, MoveNext, and MovePrevious methods (ADO)
ms:assetid: d04ce41c-77c9-df42-115a-65c50a38518a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250039(v=office.15)
ms:contentKeyID: 48547836
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2cb6ea7f82ac37460d7f2a4dd998ae7435c04230
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288783"
---
# <a name="movefirst-movelast-movenext-and-moveprevious-methods-ado"></a>MoveFirst、MoveLast、MoveNext 和 MovePrevious 方法 (ADO)


**适用于**：Access 2013、Office 2013

用于移动到指定的 [Recordset](recordset-object-ado.md) 对象中的第一个、最后一个、下一个或上一个记录，并使该记录成为当前记录。

## <a name="syntax"></a>语法

*recordset*。{ MoveFirst |MoveLast |MoveNext |MovePrevious

## <a name="remarks"></a>注解

使用 **MoveFirst** 方法可以将当前记录位置移动到 **Recordset** 中的第一个记录。

使用 **MoveLast** 方法可以将当前记录位置移动到 **Recordset** 中的最后一个记录。 **Recordset** 对象必须支持书签或向后游标移动；否则，该方法调用将生成错误。

当 **Recordset** 为空（ **BOF** 和 **EOF** 均为 True）时，调用 **MoveFirst** 或 **MoveLast** 将生成错误。

使用 **MoveNext** 方法可以将当前记录位置向前（朝着 **Recordset** 的末部）移动一个记录。如果最后一个记录就是当前记录，则调用 **MoveNext** 方法时，ADO 将把当前记录设置为 **Recordset** 中最后一个记录之后的位置（[EOF](bof-eof-properties-ado.md) 为 **True**）。当 **EOF** 属性已经为 **True** 时尝试向前移动，将生成错误。

如果已经对 **Recordset** 进行了筛选或排序，且当前记录的数据已更改，则记录的位置也可能会更改。 在这种情况下， **MoveNext** 方法仍正常工作，但您应注意，记录的位置是从新位置（而不是旧位置）向前移动一个记录。 例如, 更改当前记录中的数据, 以便将记录移动到已排序 Recordset 的末尾 **,** 这意味着调用**MoveNext**会导致 ADO 将当前记录设置为中**最后一条记录之后的位置Recordset** (**EOF** = **True**)。

使用 **MovePrevious** 方法可以将当前记录位置向后（朝着 **Recordset** 的顶部）移动一个记录。**Recordset** 对象必须支持书签或向后的游标移动；否则，该方法将生成错误。如果第一个记录就是当前记录，则调用 **MovePrevious** 方法时，ADO 将把当前记录设置为 **Recordset** 中第一个记录之前的位置（[BOF](bof-eof-properties-ado.md) 为 **True**）。当 **BOF** 属性已经为 **True** 时，尝试向后移动将生成错误。如果 **Recordset** 对象不支持书签或向后的游标移动，**MovePrevious** 方法将生成错误。

如果 **Recordset** 是仅向前的，并且您想要同时支持向前和向后滚动，则可以使用 [CacheSize](cachesize-property-ado.md) 属性来创建记录缓存，后者通过 [Move](move-method-ado.md) 方法支持向后游标移动。由于缓存的记录被加载到内存中，因此，您应该避免缓存超过所需数目的记录。可以在仅向前的 **Recordset** 对象中调用 **MoveFirst** 方法；这样做可能会导致提供程序重新执行生成 **Recordset** 对象的命令。

