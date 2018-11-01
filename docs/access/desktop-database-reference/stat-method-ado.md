---
title: Stat 方法-ActiveX 数据对象 (ADO)
TOCTitle: Stat Method (ADO)
ms:assetid: d3d3976b-14d4-dee0-412d-a37bc72fbfd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250056(v=office.15)
ms:contentKeyID: 48547916
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6e620c3b2f824f7c49abb576ea46a51b04598463
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25891154"
---
# <a name="stat-method-ado"></a>Stat 方法 (ADO)


**适用于**： Access 2013、 Office 2013

可检索有关 **Stream** 对象的信息。

## <a name="syntax"></a>语法

长*流*。Stat （*StatStg*、 *StatFlag*）

## <a name="return-value"></a>返回值

长整型值，指示操作的状态。

## <a name="parameters"></a>参数

  - *StatStg*

  - STATSTG 结构，将使用流信息进行填充。ADO Stream 对象所用的 Stat 方法的实现不会填充该结构的所有字段。

  - *StatFlag*

  - 可指定此方法不在 STATSTG 结构中返回某些成员，从而省去了内存分配操作。值从 STATFLAG 枚举中提取。  
      
    STATFLAG 枚举包括两个值：
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>常量</p></th>
    <th><p>值</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>STATFLAG_DEFAULT</p></td>
    <td><p>0</p></td>
    </tr>
    <tr class="even">
    <td><p>STATFLAG_NONAME</p></td>
    <td><p>1</p></td>
    </tr>
    </tbody>
    </table>


## <a name="remarks"></a>备注

为 ADO Stream 对象实现的 Stat 方法会填充 STATSTG 结构的以下字段：

  - *pwcsName*

  - 如果有包含流中的名称的字符串和 StatFlag 值 STATFLAG\_无名未指定。

  - *cbSize*

  - 指定流或字节数组的大小，以字节计。

  - *mtime*

  - 指示此存储、流或字节数组的上次修改时间。

  - *ctime*

  - 指示此存储、流或字节数组的创建时间。

  - *atime*

  - 指示此存储、流或字节数组的上次访问时间。

如果 STATFLAG\_在 StatFlag 参数中指定无名，则不返回流的名称。

如果 STATFLAG\_无名未在 StatFlag 参数中指定和没有可用于当前流的名称，此值将 E\_NOTIMPL。

