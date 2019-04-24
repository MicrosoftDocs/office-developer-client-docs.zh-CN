---
title: WillChangeField 和 FieldChangeComplete 事件 (ADO)
TOCTitle: WillChangeField and FieldChangeComplete events (ADO)
ms:assetid: bc4455a6-2925-33dc-d04f-8ea570e5e370
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249904(v=office.15)
ms:contentKeyID: 48547407
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0fd952cc09f410752f3eb7b5963059f8d6ee7c2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302483"
---
# <a name="willchangefield-and-fieldchangecomplete-events-ado"></a>WillChangeField 和 FieldChangeComplete 事件 (ADO)

**适用于**：Access 2013、Office 2013

**WillChangeField** 事件在挂起的操作更改 [Recordset](recordset-object-ado.md) 中的一个或多个 [Field](field-object-ado.md) 对象的值之前调用。**FieldChangeComplete** 事件在一个或多个 **Field** 对象的值已更改之后调用。

## <a name="syntax"></a>语法

WillChangeField*cFields*、 *Fields*、 *adStatus*、 *pRecordset*

FieldChangeComplete*cFields*、 *Fields*、 *pError*、 *adStatus*、 *pRecordset*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*cFields* |**长整型**值，指示 *Fields* 中 **Field** 对象的数量。|
|*Fields* |对于 **WillChangeField**，*Fields* 参数是包含具有原始值的 **Field** 对象的**变量型**数组。 <br/><br/>
对于 **FieldChangeComplete**，*Fields* 参数是包含值发生更改的 **Field** 对象的**变量型**数组。|
|*pError* |[Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。|
|*adStatus* |[EventStatusEnum](eventstatusenum.md)。 当调用**WillChangeField**时, 如果导致事件的操作成功, 则将此参数设置为**adstatusok;** 。 如果此事件无法请求取消挂起的操作, 则将其设置为**adStatusCantDeny** 。 <br/><br/>调用 **FieldChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。 <br/><br/>在 **WillChangeField** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作。 <br/><br/>在 **FieldChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。|
|*pRecordset* |**Recordset** 对象。发生此事件的 **Recordset** 。|

## <a name="remarks"></a>注解

设置 [Value](value-property-ado.md) 属性并调用带有字段和值数组参数的 [Update](update-method-ado.md) 方法时，可能会发生 **WillChangeField** 或 **FieldChangeComplete** 事件。

