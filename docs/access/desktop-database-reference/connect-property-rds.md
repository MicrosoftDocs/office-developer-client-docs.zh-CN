---
title: Connect 属性 (RDS)
TOCTitle: Connect Property (RDS)
ms:assetid: 11aa3284-18e9-6d2d-761b-c25090370b77
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248890(v=office.15)
ms:contentKeyID: 48543324
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: eb628356e4d93201c38cf84a9c3245b13e044ee3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468267"
---
# <a name="connect-property-rds"></a>Connect 属性 (RDS)


**适用于**： Access 2013 |Office 2013

指示在其中运行查询和更新操作的数据库的名称。

可在设计时在 **RDS.DataControl** 对象的 OBJECT 标记中设置 [Connect](datacontrol-object-rds.md) 属性，或在运行时在脚本代码（例如，VBScript）中设置此属性。

## <a name="syntax"></a>语法

设计时：\<参数名称 ="连接"值 ="ConnectionString"\>

运行时间： DataControl.Connect ="ConnectionString"

## <a name="parameters"></a>参数

  - *ConnectionString*

  - 有效的连接字符串。有关连接字符串的详细常规信息，请参阅 [ConnectionString](connectionstring-property-ado.md) 属性或提供程序文档。
    

    > [!NOTE]
    > <P>[!注释] 将 MS Remote 指定为 <STRONG>RDS.DataControl</STRONG> 的提供程序将创建一个四层方案。大于三层的方案均未经过测试，应该不会有此方面的需要。</P>



  - *DataControl*

  - 一个代表 **RDS.DataControl** 对象的对象变量。

