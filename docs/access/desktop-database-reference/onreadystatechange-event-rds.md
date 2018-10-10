---
title: onReadyStateChange 事件 (RDS)
TOCTitle: onReadyStateChange Event (RDS)
ms:assetid: 88102ee5-cca9-8ccb-5aca-55cda71abc4d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249593(v=office.15)
ms:contentKeyID: 48546126
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: dec783aaa76745b73bd031b00f1b8587a58eb165
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467709"
---
# <a name="onreadystatechange-event-rds"></a>onReadyStateChange 事件 (RDS)


**适用于**： Access 2013 |Office 2013


只要 **ReadyState** 属性的值发生更改，便会调用 [onReadyStateChange](readystate-property-rds.md) 事件。

## <a name="syntax"></a>语法

onReadyStateChange

## <a name="parameters"></a>参数

无。

## <a name="remarks"></a>备注

**ReadyState** 属性反映 [RDS.DataControl](datacontrol-object-rds.md) 对象在以异步方式将数据检索到其 [Recordset](recordset-object-ado.md) 对象中时的进度。使用 **onReadyStateChange** 事件来监视 **ReadyState** 属性中随时发生的变化。这比定期检查属性值效率更高。

