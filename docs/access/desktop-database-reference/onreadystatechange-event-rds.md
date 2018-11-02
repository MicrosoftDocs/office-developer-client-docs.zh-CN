---
title: onReadyStateChange 事件 (RDS)
TOCTitle: onReadyStateChange event (RDS)
ms:assetid: 88102ee5-cca9-8ccb-5aca-55cda71abc4d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249593(v=office.15)
ms:contentKeyID: 48546126
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3e52ef236a5e57efc965a6b3bd8ab6edd7533f2c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922207"
---
# <a name="onreadystatechange-event-rds"></a>onReadyStateChange 事件 (RDS)


**适用于**： Access 2013、 Office 2013


只要 **ReadyState** 属性的值发生更改，便会调用 [onReadyStateChange](readystate-property-rds.md) 事件。

## <a name="syntax"></a>语法

onReadyStateChange

## <a name="parameters"></a>参数

无。

## <a name="remarks"></a>备注

**ReadyState** 属性反映 [RDS.DataControl](datacontrol-object-rds.md) 对象在以异步方式将数据检索到其 [Recordset](recordset-object-ado.md) 对象中时的进度。使用 **onReadyStateChange** 事件来监视 **ReadyState** 属性中随时发生的变化。这比定期检查属性值效率更高。

