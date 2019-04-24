---
title: Handler 属性 (RDS)
TOCTitle: Handler property (RDS)
ms:assetid: aaf8c8c6-f95b-3cf3-b3f6-203f37464c87
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249792(v=office.15)
ms:contentKeyID: 48546962
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c3ad91f0a288b9908a5af5f92d7bfca3b23cdfe9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292067"
---
# <a name="handler-property-rds"></a>Handler 属性 (RDS)

**适用于**：Access 2013、Office 2013

指示扩展 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 功能的服务器端自定义程序（处理程序）的名称和该*处理程序*使用的任何参数。

## <a name="syntax"></a>语法

*rds.datacontrol*。处理程序 = *String*

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*DataControl* |一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。|
|*String* |一个**字符串**值, 包含处理程序的名称和任何参数, 均由逗号分隔 (例如, "handlerName, parm1, parm2,..., parm *N*")。|

## <a name="remarks"></a>注解

此属性支持自定义，对自定义功能的支持需要将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient**。

处理程序的名称及其参数（如果有）均由逗号（“,”） 分隔。如果分号（“;”）在 *String* 中的位置不固定，则会导致不可预知的行为。如果处理程序支持 **IDataFactoryHandler** 接口，则可以编写自己的处理程序。

默认处理程序的名称为 **MSDFMAP.Handler** ，其默认参数是名为 **MSDFMAP.INI** 的自定义文件。使用此属性可调用由服务器管理员创建的备用自定义文件。

设置**handler**属性的另一种方法是在[ConnectionString](connectionstring-property-ado.md)属性中指定处理程序和参数;即 "**Handler = * * * handlerName, parm1, parm2,...;*"。

