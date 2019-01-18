---
title: Database.ReplicaID 属性 (DAO)
TOCTitle: ReplicaID Property
ms:assetid: cf2ca8a1-d13f-30e0-2ca1-dd32ac736c56
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834672(v=office.15)
ms:contentKeyID: 48547805
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053375
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2ada9bf23a4b8fc34c5f9b4f24350fc6af91dc85
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703928"
---
# <a name="databasereplicaid-property-dao"></a>Database.ReplicaID 属性 (DAO)


**适用于**： Access 2013、 Office 2013


返回一个 16 字节的值，该值唯一标识数据库副本（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。ReplicaID

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

返回值是一个 **GUID** 值，该值唯一标识副本或设计母版。

在您创建新副本时，Microsoft Access 数据库引擎自动生成这个值。

每个副本（和设计母版）的 **ReplicaID** 属性都存储在 MSysReplicas 系统表中。

## <a name="example"></a>示例

以下示例从 Northwind.mdb 的设计母版生成副本，然后返回 Microsoft Access 数据库引擎自动创建的副本 **ReplicaID**。（如果您尚未创建 Northwind 数据库的设计母版，请引用 **Replicable** 属性或者将代码中数据库的名称更改为现有设计母版。）

```vb 
Sub MakeReplicaReplicaIDX() 
 
 Dim dbsNorthwind As Database 
 Dim prpReplicaID As Property 
 Dim dbsReplica As Database 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Makes a new replica. 
 dbsNorthwind.MakeReplica "Nwreplica2.mdb", _ 
 "second replica" 
 dbsNorthwind.Close 
 
 ' Opens the new replica to read its ReplicaID. 
 Set dbsReplica = OpenDatabase("Nwreplica2.mdb") 
 
 Debug.Print dbsReplica.ReplicaID 
 dbsReplica.Close 
 
End Sub 
 
```

