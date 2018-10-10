---
title: Database.DesignMasterID Property (DAO)
TOCTitle: DesignMasterID Property
ms:assetid: c0545561-d44f-5479-8ae0-e3955db91761
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822824(v=office.15)
ms:contentKeyID: 48547508
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053417
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 0bb2e369f886ba60fb425b9f1f2d10fdea0c1463
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467257"
---
# <a name="databasedesignmasterid-property-dao"></a>Database.DesignMasterID Property (DAO)

**适用于**： Access 2013 |Office 2013

设置或返回一个 16 字节值，该值唯一地标识副本集中的设计母版（仅适用于 Microsoft Access 工作区）。

## <a name="syntax"></a>语法

*表达式*。DesignMasterID

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

仅当您需要移动当前的设计母版时，才应该设置 **DesignMasterID** 属性。设置该属性将使副本集中的特定副本成为设计母版。

> [!NOTE]
> [!注释] 切勿在副本集中创建另一个设计母版。如果存在另一个设计母版，则可能导致数据丢失。

在极端条件下（例如，设计母版被清除或损坏），可以在当前副本上设置该属性。但是，如果副本集中已经存在另一个设计母版，则在一个副本上设置该属性可能会将副本集划分成两个不可协调的集合，并且会阻止此后进行任何数据同步。

如果决定使某个副本成为副本集的新设计母版，请在该副本中设置 **DesignMasterID** 属性之前，使该副本与副本集中的所有副本同步。要使副本成为设计母版，该副本必须以独占模式打开。

如果要使一个指定为只读的副本成为设计母版，则应该将目标副本设置为可读写；旧的设计母版同样应保持为可读写。

**DesignMasterID** 属性设置存储在 MSysRepInfo 系统表中。

## <a name="example"></a>示例

以下示例将 **DesignMasterID** 属性设置为另一个数据库的 **ReplicaID** 属性设置，从而使该数据库成为副本集中的设计母版。新旧设计母版将进行同步以更新设计更改。若要使该代码工作，必须创建一个设计母版和副本，再根据需要包括其名称和路径，然后从数据库（而不是新的或旧的设计母版）运行该代码。

```vb 
 Sub SetNewDesignMaster(strOldDM as String, _ 
    strNewDM as String) 
    
    Dim dbsOld As Database 
    Dim dbsNew As Database 
    
    ' Open the current Design Master in exclusive mode. 
    Set dbsOld = OpenDatabase(strOldDM, True) 
    
    ' Open the database that will become the new 
    ' Design Master. 
    Set dbsNew = OpenDatabase(strNewDM) 
    
    ' Make the new database the Design Master. 
    dbsOld.DesignMasterID = dbsNew.ReplicaID 
    
    ' Synchronize the old Design Master with the new 
    ' Design Master, and allow two-way exchanges. 
    dbsOld.Synchronize strNewDM, dbRepImpExpChanges 
    dbsOld.Close 
    dbsNew.Close 
 
 End Sub 
 
```

