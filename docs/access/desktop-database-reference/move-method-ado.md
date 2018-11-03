---
title: Move 方法-ActiveX 数据对象 (ADO)
TOCTitle: Move method (ADO)
ms:assetid: 1f858654-5fa3-273d-7cdc-574c5f09a420
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248982(v=office.15)
ms:contentKeyID: 48543645
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 30feb9aabeb84c577b415b2872ce407cf3fc0f44
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950004"
---
# <a name="move-method-ado"></a>Move 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于移动 [Recordset](recordset-object-ado.md) 对象中当前记录的位置。

## <a name="syntax"></a>语法

*记录集*。移动*NumRecords*，*启动*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*NumRecords* |有符号的 **长整型** 表达式，指定当前记录位置移动的记录数。|
|*Start* |可选。 **字符串型** 值或值为书签的 **变量型** 值。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。|

## <a name="remarks"></a>备注

所有的 **Recordset** 对象都支持 **Move** 方法。

如果 *NumRecords* 参数大于零，则当前记录的位置会（朝着 **Recordset** 的末尾）向前移动；如果 *NumRecords* 小于零，则当前记录的位置会（朝着 **Recordset** 的开头）向后移动。

如果**Move**调用会将当前记录位置移动到第一个记录之前的点，ADO 会将当前记录设置为第一个记录之前记录集中的位置 （[BOF](bof-eof-properties-ado.md)为**True**）。 当 **BOF** 属性已经为 **True** 时，尝试向后移动将生成错误。

如果**Move**调用会后的最后一个记录移动了到某个点的当前记录位置，ADO 将当前记录位置设置 （[EOF](bof-eof-properties-ado.md)为**True**） 将 recordset 中的最后一个记录之后。 当 **EOF** 属性已经为 **True** 时尝试向前移动将生成错误。

从空 **Recordset** 对象调用 **Move** 方法将生成错误。

如果*Start*参数传递，移动是相对于包含该书签，假定**Recordset**对象支持书签记录。 如果未指定该参数，则将相对于当前的记录进行移动。

如果您正在从提供程序，将移动外部的缓存记录当前的组的当前记录位置*NumRecords*参数传递到本地缓存记录使用[CacheSize](cachesize-property-ado.md)属性强制 ADO 检索一组新记录，从目标记录开始。 **CacheSize** 属性确定新检索组的大小，目标记录是检索到的第一个记录。

如果**Recordset**对象仅转接，则用户提供当前的缓存记录集内的目标是仍可以传递*NumRecords*参数小于零。 如果 **Move** 调用会使当前记录位置移动到第一个缓存的记录之前的某个记录，将发生错误。 因此，您可以通过支持仅向前滚动的提供程序来使用支持前后滚动的记录缓存。 由于缓存的记录被加载到内存中，应该避免缓存超过所需数目的记录。 即使仅向前的 **Recordset** 对象支持以这种方式向后移动，对任何仅向前的 [Recordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 对象调用 **MovePrevious** 方法仍然会生成错误。


> [!NOTE]
> [!注释] 对在仅向前的 **Recordset** 中向后移动的支持是不可预测的，具体取决于您的提供程序。如果当前记录已定位在 **Recordset** 中最后一个记录之后，则向后 **移动** 不会获得正确的当前位置。


