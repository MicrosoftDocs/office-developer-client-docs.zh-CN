---
title: ConvertToString 方法 (RDS)
TOCTitle: ConvertToString method (RDS)
ms:assetid: dc6381e4-98c8-badc-ad8c-87c70574a8a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250113(v=office.15)
ms:contentKeyID: 48548136
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0accdb33aecacdb6bb6c51a3ec1a39d2edb08ead
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949444"
---
# <a name="converttostring-method-rds"></a>ConvertToString 方法 (RDS)

**适用于**： Access 2013、 Office 2013 

将 [Recordset](recordset-object-ado.md) 转换为代表记录集数据的 MIME 字符串。

## <a name="syntax"></a>语法

*DataFactory*。ConvertToString (*Recordset*)

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*DataFactory* |一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。|
|*Recordset* |一个代表 **Recordset** 对象的对象变量。|

## <a name="remarks"></a>说明

利用 .asp 文件，使用 **ConvertToString** 将 **Recordset** 嵌入到服务器上生成的 HTML 页，以将该记录集传输到客户端计算机。

**ConvertToString** 首先将 **Recordset** 加载到"游标服务"表中，然后生成 MIME 格式的流。

在客户端，远程数据服务可以将 MIME 字符串转换回功能完整的 **Recordset** 。这种功能可以很好地处理少于 400 行、每行宽度不超过 1024 字节的数据。但在通过 HTTP 在以流方式传输 BLOB 数据和较大的结果集时，不应使用该功能。在字符串上不会执行在线压缩，因此与由远程数据服务定义和部署为其自己的传输协议格式的在线优化的表图格式相比，很大的数据集在通过 HTTP 传输时将花费相当长的时间。

> [!NOTE]
> [!注释] 如果要使用 Active Server 页将生成的 MIME 字符串嵌入客户端 HTML 页，请注意低于 2.0 版的 VBScript 会将字符串大小限制为 32K。如果超过此限制，将返回一个错误。通过 .asp 文件使用 MIME 嵌入功能时，请保持相对较小的查询范围。若要修复此问题，请从 [Microsoft 下载中心](https://www.microsoft.com/download/default.aspx)下载最新版本的 VBScript。


