---
title: EditMode 属性 (ADO)
TOCTitle: EditMode property (ADO)
ms:assetid: 28ca8f14-abee-ad20-9c16-11bb36b487e4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249045(v=office.15)
ms:contentKeyID: 48543867
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7d7bba0af804df89bf4c8611e184928c9bf12d55
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293607"
---
# <a name="editmode-property-ado"></a>EditMode 属性 (ADO)


**适用于**：Access 2013、Office 2013

指示当前记录的编辑状态。

## <a name="return-value"></a>返回值

返回 [EditModeEnum](editmodeenum.md) 值。

## <a name="remarks"></a>注解

ADO 维护着一个与当前记录关联的编辑缓冲区。此属性指示是否对此缓冲区进行了更改，或是否创建了新记录。通过使用 **EditMode** 属性，可以确定当前记录的编辑状态。如果编辑进程已中断，可以检测是否存在待定更改，并确定是否需要使用 [Update](update-method-ado.md) 或 [CancelUpdate](cancelupdate-method-ado.md) 方法。

有关 [EditMode](addnew-method-ado.md) 属性在各种不同编辑情况下的更为详细的说明，请参阅 **AddNew** 方法。

调用[delete](delete-method-ado-recordset.md)不能成功删除数据源 (例如, 由于参照完整性违规) 中的记录或记录时, [Recordset](recordset-object-ado.md)仍处于编辑模式 (**EditMode** = **adEditInProgress**). 这意味着在从当前记录移动到别的位置（例如，使用 **Move**、[NextRecordset](move-method-ado.md) 或 [Close](nextrecordset-method-ado.md)）前，必须调用 [CancelUpdate](close-method-ado.md) 。


> [!NOTE]
> [!注释] **EditMode** 仅在存在当前记录时才能返回有效值。如果 **BOF 或 EOF** 为 True 或当前记录已删除， [EditMode](bof-eof-properties-ado.md) 将返回错误。


