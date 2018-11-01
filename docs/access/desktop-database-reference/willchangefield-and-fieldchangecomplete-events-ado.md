---
title: WillChangeField 和 FieldChangeComplete 事件 (ADO)
TOCTitle: WillChangeField and FieldChangeComplete Events (ADO)
ms:assetid: bc4455a6-2925-33dc-d04f-8ea570e5e370
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249904(v=office.15)
ms:contentKeyID: 48547407
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: aa26ff85bfb3a2b5666b98ea6ab6b30e689b5c2b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872688"
---
# <a name="willchangefield-and-fieldchangecomplete-events-ado"></a>WillChangeField 和 FieldChangeComplete 事件 (ADO)


**适用于**： Access 2013、 Office 2013

**WillChangeField** 事件在挂起的操作更改 [Recordset](field-object-ado.md) 中的一个或多个 [Field](recordset-object-ado.md) 对象的值之前调用。 **FieldChangeComplete** 事件在一个或多个 **Field** 对象的值已更改之后调用。

## <a name="syntax"></a>语法

WillChangeField*cFields*，*字段*， *adStatus* *pRecordset*

FieldChangeComplete*cFields*，*字段*， *pError* *adStatus*、 *pRecordset*

## <a name="parameters"></a>参数

  - *cFields*

  - **长整型**值，指示 *Fields* 中 **Field** 对象的数量。

  - *Fields*

  - 对于**WillChangeField**，*字段*参数是包含的原始值与**Field**对象的**变量**的数组。  
      
    对于**FieldChangeComplete**，*字段*参数是包含更改的值与**Field**对象的**变量**的数组。

  - *pError*

  - [Error](error-object-ado.md) 对象。如果 *adStatus* 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    调用 **WillChangeField** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果此事件无法请求取消挂起操作，则该参数设置为 **adStatusCantDeny** 。
    
    调用 **FieldChangeComplete** 时，如果导致事件的操作成功，则该参数设置为 **adStatusOK** ；如果导致事件的操作失败，则该参数设置为 **adStatusErrorsOccurred** 。
    
    在 **WillChangeField** 返回之前，将该参数设置为 **adStatusCancel** 可以请求取消挂起的操作。
    
    在 **FieldChangeComplete** 返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。

  - *pRecordset*

  - **Recordset** 对象。发生此事件的 **Recordset** 。

## <a name="remarks"></a>备注

设置 **Value** 属性并调用带有字段和值数组参数的 **Update** 方法时，可能会发生 [WillChangeField](value-property-ado.md) 或 [FieldChangeComplete](update-method-ado.md) 事件。

