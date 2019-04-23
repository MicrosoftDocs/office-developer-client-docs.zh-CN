---
title: onReadyStateChange 事件 (RDS)
TOCTitle: onReadyStateChange event (RDS)
ms:assetid: 88102ee5-cca9-8ccb-5aca-55cda71abc4d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249593(v=office.15)
ms:contentKeyID: 48546126
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ec2104634d9158d59d488b50d543cf0e57d9bd62
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288488"
---
# <a name="onreadystatechange-event-rds"></a>onReadyStateChange 事件 (RDS)

**适用于**：Access 2013、Office 2013

只要 [ReadyState](readystate-property-rds.md) 属性的值发生更改，便会调用 **onReadyStateChange** 事件。

## <a name="syntax"></a>语法

onReadyStateChange

## <a name="parameters"></a>参数

无。

## <a name="remarks"></a>注解

**ReadyState** 属性反映 [RDS.DataControl](datacontrol-object-rds.md) 对象在以异步方式将数据检索到其 [Recordset](recordset-object-ado.md) 对象中时的进度。使用 **onReadyStateChange** 事件来监视 **ReadyState** 属性中随时发生的变化。这比定期检查属性值效率更高。

