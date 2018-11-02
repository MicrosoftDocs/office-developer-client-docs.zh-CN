---
title: WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)
TOCTitle: WillChangeRecordset and RecordsetChangeComplete events (ADO)
ms:assetid: 2cec4cf9-a4e9-c386-5202-04e86f4cf8ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249068(v=office.15)
ms:contentKeyID: 48543963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ac85cd672a07d65b19578daa8ca737af584972a2
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919141"
---
# <a name="willchangerecordset-and-recordsetchangecomplete-events-ado"></a>WillChangeRecordset 和 RecordsetChangeComplete 事件 (ADO)


**适用于**： Access 2013、 Office 2013


**WillChangeRecordset** 事件在挂起的操作更改 [Recordset](recordset-object-ado.md) 之前调用。 **RecordsetChangeComplete** 事件在 **Recordset** 已更改之后调用。

## <a name="syntax"></a>语法

在 WillChangeRecordset*adReason*， *adStatus* *pRecordset*

RecordsetChangeComplete*adReason* *pError*、 *adStatus*、 *pRecordset*

## <a name="parameters"></a>参数

  - *adReason*

  - 指定此事件原因的 [EventReasonEnum](eventreasonenum.md) 值。其值可以是 **adRsnRequery** 、 **adRsnResynch** 、 **adRsnClose** 和 **adRsnOpen** 。

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    调用 **WillChangeRecordset** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。
    
    调用 **RecordsetChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果操作失败，则该参数设置为 **adStatusErrorsOccurred** ；如果与以前接受的 **WillChangeRecordset** 事件关联的操作已被取消，则该参数设置为 **adStatusCancel** 。
    
    在 **WillChangeRecordset** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作，将该参数设置为 adStatusUnwantedEvent 可以阻止随后进行通知。
    
    在 **WillChangeRecordset** 或 **RecordsetChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。

  - *pError*

  - [Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。

  - *pRecordset*

  - **Recordset** 对象。发生此事件的 **Recordset** 。

## <a name="remarks"></a>备注

**WillChangeRecordset**或**RecordsetChangeComplete**事件可能发生的**Recordset**的[Requery](requery-method-ado.md)或[Open](open-method-ado-recordset.md)方法。

如果提供程序不支持书签，则每次从提供程序检索新行时，会发生 **RecordsetChange** 事件通知。该事件的频率取决于 **RecordsetCacheSize** 属性。

对于每个可能的 **adReason** 值，必须将 **adStatus** 参数设置为 **adStatusUnwantedEvent** ，才能完全阻止包括 **adReason** 参数的任何事件的事件通知。

