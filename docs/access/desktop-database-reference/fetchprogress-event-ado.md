---
title: FetchProgress 事件 (ADO)
TOCTitle: FetchProgress event (ADO)
ms:assetid: 09145d9a-ea5e-b41c-6c54-33ec83e642a9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248828(v=office.15)
ms:contentKeyID: 48543114
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 929202df2d85ba2a4625a94506f8515eaba9fb39
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25923684"
---
# <a name="fetchprogress-event-ado"></a>FetchProgress 事件 (ADO)


**适用于**： Access 2013、 Office 2013


**FetchProgress** 事件在持续时间很长的异步操作中定期调用，以报告当前又另外将多少行检索到了 [Recordset](recordset-object-ado.md) 中。

## <a name="syntax"></a>语法

FetchProgress*进度*， *MaxProgress*， *adStatus* *pRecordset*

## <a name="parameters"></a>参数

  - *Progress*

  - **长整型** 值，指示提取操作当前检索的记录数。

  - *MaxProgress*

  - **长整型** 值，指示预期检索到的最多记录数。

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md) 状态值。

  - *pRecordset*

  - **Recordset** 对象，即要为其检索记录的对象。

## <a name="remarks"></a>说明

当子**Recordset**中使用**FetchProgress** ，都可以识别的*进度*和*MaxProgress*参数值派生基础[Cursor Service](microsoft-cursor-service-for-ole-db-ado-service-component.md)行集。 返回的值代表基础行集中的记录总数，而不仅仅是当前章节中的记录数。


> [!NOTE]
> [!注释] 若要在 Microsoft Visual Basic 中使用 **FetchProgress** ，需要 Visual Basic 6.0 或更高版本。


