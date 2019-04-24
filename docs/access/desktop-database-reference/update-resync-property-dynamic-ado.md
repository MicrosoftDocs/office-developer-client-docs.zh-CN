---
title: 更新 Resync 动态属性 (ADO)
TOCTitle: Update Resync dynamic property (ADO)
ms:assetid: 0af9cfd2-8042-65c9-cec6-77d2e7a88ad9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248842(v=office.15)
ms:contentKeyID: 48543166
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 653291ade258d602d7ec523dcac7e9fe51dd91fb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308342"
---
# <a name="update-resync-dynamic-property-ado"></a>更新 Resync 动态属性 (ADO)


**适用于**：Access 2013、Office 2013

指定 [UpdateBatch](updatebatch-method-ado.md) 方法后面是否跟随隐式的 [Resync](resync-method-ado.md) 方法操作，如果跟随，则指定该操作的范围。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个或多个[\_ADCPROP UPDATERESYNC\_枚举](adcprop-updateresync-enum.md)值。

## <a name="remarks"></a>注解

ADCPROP\_UPDATERESYNC\_枚举的值可能会组合在一起, 但已代表其余值的组合的 adResyncAll 除外。

常量 **adResyncConflicts** 会将各个重新同步值作为基础值存储，但不会重写待定的更改。

**Update Resync** 是一个动态属性，会在 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 时追加到 [Recordset](recordset-object-ado.md) 对象的 [Properties](properties-collection-ado.md) 集合中。

