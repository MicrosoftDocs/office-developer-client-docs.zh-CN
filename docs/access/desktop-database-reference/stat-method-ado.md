---
title: Stat 方法-ActiveX 数据对象 (ADO)
TOCTitle: Stat method (ADO)
ms:assetid: d3d3976b-14d4-dee0-412d-a37bc72fbfd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250056(v=office.15)
ms:contentKeyID: 48547916
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 853d89bde9184bd546b3e7df9e8eda287faf86c9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28721071"
---
# <a name="stat-method-ado"></a>Stat 方法 (ADO)

**适用于**： Access 2013、 Office 2013

可检索有关 **Stream** 对象的信息。

## <a name="syntax"></a>语法

长*流*。Stat （*StatStg*、 *StatFlag*）

## <a name="return-value"></a>返回值

长整型值，指示操作的状态。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*StatStg* |STATSTG 结构，将使用流信息进行填充。ADO Stream 对象所用的 Stat 方法的实现不会填充该结构的所有字段。|
|*StatFlag* |可指定此方法不在 STATSTG 结构中返回某些成员，从而省去了内存分配操作。值从 STATFLAG 枚举中提取。<br/><br/>STATFLAG 枚举具有两个值：<br/>-STATFLAG_DEFAULT: 0<br/>-STATFLAG_NONAME: 1 |


## <a name="remarks"></a>备注

为 ADO Stream 对象实现的 Stat 方法会填充 STATSTG 结构的以下字段：

|字段|说明|
|:--------|:----------|
|*pwcsName* |如果有包含流中的名称的字符串和 StatFlag 值 STATFLAG\_无名未指定。|
|*cbSize* |指定流或字节数组的大小，以字节计。|
|*mtime* |指示此存储、流或字节数组的上次修改时间。|
|*ctime* |指示此存储、流或字节数组的创建时间。|
|*atime* |指示此存储、流或字节数组的上次访问时间。|

如果 STATFLAG\_在 StatFlag 参数中指定无名，则不返回流的名称。

如果 STATFLAG\_无名未在 StatFlag 参数中指定和没有可用于当前流的名称，此值将 E\_NOTIMPL。

