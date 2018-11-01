---
title: Create 方法 (ADOX)
TOCTitle: Create Method (ADOX)
ms:assetid: d4072ee7-a0b9-7780-7be0-1d64b42b437c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250060(v=office.15)
ms:contentKeyID: 48547924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 91f5105611df85e007dea6d0e17e3104ea5987a3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870252"
---
# <a name="create-method-adox"></a>Create 方法 (ADOX)


**适用于**： Access 2013、 Office 2013


创建新目录。

## <a name="syntax"></a>语法

*目录*。创建*ConnectString*

## <a name="parameters"></a>参数

  - *ConnectString*

  - 一个用来连接数据源的 **String** 值。

## <a name="remarks"></a>说明

**Create** 方法创建一个新 ADO [Connection](connection-object-ado.md) 并打开它，该对象连接到在 *ConnectString* 中指定的数据源。如果成功，该新 **Connection** 对象将被分配给 [ActiveConnection](activeconnection-property-adox.md) 属性。

如果提供程序不支持创建新目录，则会发生错误。

