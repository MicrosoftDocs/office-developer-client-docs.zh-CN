---
title: FetchComplete 事件 (ADO)
TOCTitle: FetchComplete event (ADO)
ms:assetid: 4863d5b5-7d77-bdef-c511-f85c9e6dec9d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249224(v=office.15)
ms:contentKeyID: 48544621
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ed0f93fc8b58d94675377b3263ba60fb692a9a4e
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949488"
---
# <a name="fetchcomplete-event-ado"></a>FetchComplete 事件 (ADO)

**适用于**： Access 2013、 Office 2013

**FetchComplete** 事件在持续时间很长的异步操作中的所有记录都已检索到 [Recordset](recordset-object-ado.md) 中之后发生。

## <a name="syntax"></a>语法

FetchComplete*pError*， *adStatus* *pRecordset*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*pError* |[Error](error-object-ado.md) 对象。如果 **adStatus** 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pRecordset* |**Recordset** 对象。为其检索记录的对象。|

## <a name="remarks"></a>备注

若要在 Microsoft Visual Basic 中使用 **FetchComplete** ，需要 Visual Basic 6.0 或更高版本。

