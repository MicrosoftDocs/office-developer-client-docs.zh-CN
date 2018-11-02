---
title: Cancel 方法 (RDS)
TOCTitle: Cancel method (RDS)
ms:assetid: 08f667c2-7a3f-c2e7-7bdf-3eb533defa33
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248827(v=office.15)
ms:contentKeyID: 48543109
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: afe7a01cf00cfc432757e7c6289d0e9eabc5bc0a
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920121"
---
# <a name="cancel-method-rds"></a>Cancel 方法 (RDS)


**适用于**： Access 2013、 Office 2013

用于取消执行挂起的异步方法调用。

## <a name="syntax"></a>语法

*RDS*。 *DataControl*。取消

## <a name="remarks"></a>备注

当调用 **Cancel** 时， [ReadyState](readystate-property-rds.md) 会自动设置为 **adcReadyStateLoaded** ，并且 [Recordset](recordset-object-ado.md) 将为空。

