---
title: URL 属性 (RDS-访问桌面数据库引用)
TOCTitle: URL property (RDS)
ms:assetid: 722765dc-f89c-0131-73b1-69c56a795546
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249457(v=office.15)
ms:contentKeyID: 48545603
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f75e5e1a6d4df21970eea387ecd85ac8ef346a70
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25943771"
---
# <a name="url-property-rds"></a>URL 属性 (RDS)


**适用于**： Access 2013、 Office 2013



指示包含相对或绝对 URL 的字符串。

可在设计时在 **DataControl** 对象的 OBJECT 标记中设置 [URL](datacontrol-object-rds.md) 属性，或者在运行时在脚本代码中设置此属性。

## <a name="syntax"></a>语法

设计时：\<参数名称 = 值"URL"="服务器"\>

运行时间： DataControl.URL="Server"

## <a name="parameters"></a>参数

- *Server*

  - 包含有效 URL 的 **String** 值。

- *DataControl*

  - 一个代表 **DataControl** 对象的对象变量。

## <a name="remarks"></a>备注

通常，URL 标识 Active Server Page (.asp) 文件，该文件可产生并返回 [Recordset](recordset-object-ado.md)。因此，用户可以获取 **Recordset** ，而不必调用服务器端 [DataFactory](datafactory-object-rdsserver.md) 对象或设计自定义业务对象。

如果设置了 **URL** 属性，则 [SubmitChanges](submitchanges-method-rds.md) 将更改提交到 URL 指定的位置。

