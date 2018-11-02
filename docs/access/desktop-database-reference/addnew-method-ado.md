---
title: AddNew 方法 (ADO)
TOCTitle: AddNew method (ADO)
ms:assetid: bae09be0-5707-4f38-9c74-0acd0f29dbac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249899(v=office.15)
ms:contentKeyID: 48547384
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 379aa71ad875213ab8c1ae022f7c8af3350b2662
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927744"
---
# <a name="addnew-method-ado"></a>AddNew 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于为可更新的 [Recordset](recordset-object-ado.md) 对象创建新记录。

## <a name="syntax"></a>语法

*记录集*。AddNew *FieldList**值*

## <a name="parameters"></a>参数

  - *recordset*

  - **Recordset** 对象。

  - *FieldList*

  - 可选。单个名称，或新记录中字段名称或序号位置的数组。

  - *Values*

  - 可选。 单个值，或新记录中字段值的数组。 如果*Fieldlist*是一个数组，*值*还必须具有相同数量的成员; 数组否则，将发生错误。 在每个数组中，字段名称的次序必须与字段值的次序匹配。

## <a name="remarks"></a>备注

**AddNew** 方法用于创建和初始化新记录。可以结合使用 [Supports](supports-method-ado.md) 方法和 **adAddNew** （ [CursorOptionEnum](cursoroptionenum.md) 值），以检验能否在当前 **Recordset** 对象中添加记录。

调用 **AddNew** 方法之后，新记录将变为当前记录，并在调用 [Update](update-method-ado.md) 方法之后保持为当前记录。由于新记录将追加到 **Recordset** ，因此，如果在调用 Update 之后调用 **MoveNext** ，则将移动到 **Recordset** 结尾之后，从而使 **EOF** 为 True。如果 **Recordset** 对象不支持书签，那么一旦您移动到其他记录，便可能无法访问新记录。根据游标类型的不同，您可能需要调用 [Requery](requery-method-ado.md) 方法以使新记录可访问。

如果在编辑当前记录或添加新记录时调用 **AddNew** ，则 ADO 会调用 **Update** 方法来保存所有更改，然后创建新记录。

**AddNew**方法的行为取决于**Recordset**对象以及是否传递*Fieldlist*和*Values*参数的更新模式。

在*即时更新模式*下（在该模式下，只要调用 **Update** 方法，提供程序便将更改写入基础数据源），不采用参数调用 **AddNew** 参数会将 [EditMode](editmode-property-ado.md) 属性设置为 **adEditAdd**（[EditModeEnum](editmodeenum.md) 值）。提供程序将任意字段值更改缓存在本地。调用 **Update** 方法会将新记录发布到数据库并将 **EditMode** 属性重置为 **adEditNone**（**EditModeEnum** 值）。如果传递 *Fieldlist* 和 *Values* 参数，则 ADO 立即将新记录发布到数据库（无需调用 **Update**），且 **EditMode** 属性值不变 (**adEditNone**)。

以*批更新模式*（顺序提供程序缓存多个更改和将它们写入到基础数据源，仅在调用[UpdateBatch](updatebatch-method-ado.md)方法），调用不带参数的**AddNew**方法将**EditMode**设置属性设置为**adEditAdd**。 提供程序在本地缓存所有字段值的更改。 调用 **Update** 方法会将新记录添加到当前 **Recordset** 并将 **EditMode** 属性重新设置为 **adEditNone** ，但是在调用 **UpdateBatch** 方法之前，提供程序不会将更改张贴到基础数据库中。 如果传递*Fieldlist*和*Values*参数，ADO 将新记录发送到用于存储缓存; 中的提供程序您需要调用**UpdateBatch**方法发布到基础数据库的新记录。

