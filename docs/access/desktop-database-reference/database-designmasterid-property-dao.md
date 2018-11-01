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
ms.openlocfilehash: da9619102a955c9a7945d05e89a1e132371d2461
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868404"
---
# <a name="databasedesignmasterid-property-dao"></a><span data-ttu-id="c24e8-102">Database.DesignMasterID Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="c24e8-102">Database.DesignMasterID Property (DAO)</span></span>

<span data-ttu-id="c24e8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c24e8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c24e8-104">设置或返回一个 16 字节值，该值唯一地标识副本集中的设计母版（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="c24e8-104">Sets or returns a 16-byte value that uniquely identifies the Design Master in a replica set (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="c24e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="c24e8-105">Syntax</span></span>

<span data-ttu-id="c24e8-106">*表达式*。DesignMasterID</span><span class="sxs-lookup"><span data-stu-id="c24e8-106">*expression* .DesignMasterID</span></span>

<span data-ttu-id="c24e8-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c24e8-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c24e8-108">注解</span><span class="sxs-lookup"><span data-stu-id="c24e8-108">Remarks</span></span>

<span data-ttu-id="c24e8-p101">仅当您需要移动当前的设计母版时，才应该设置 **DesignMasterID** 属性。设置该属性将使副本集中的特定副本成为设计母版。</span><span class="sxs-lookup"><span data-stu-id="c24e8-p101">You should set the **DesignMasterID** property only if you need to move the current Design Master. Setting this property makes a specific replica in the replica set the Design Master.</span></span>

> [!NOTE]
> <span data-ttu-id="c24e8-p102">[!注释] 切勿在副本集中创建另一个设计母版。如果存在另一个设计母版，则可能导致数据丢失。</span><span class="sxs-lookup"><span data-stu-id="c24e8-p102">Never create a second Design Master in a replica set. The existence of a second Design Master can result in the loss of data.</span></span>

<span data-ttu-id="c24e8-p103">在极端条件下（例如，设计母版被清除或损坏），可以在当前副本上设置该属性。但是，如果副本集中已经存在另一个设计母版，则在一个副本上设置该属性可能会将副本集划分成两个不可协调的集合，并且会阻止此后进行任何数据同步。</span><span class="sxs-lookup"><span data-stu-id="c24e8-p103">Under extreme circumstances— for example, if the Design Master is erased or corrupted— you can set this property at the current replica. However, setting this property at a replica when there is already another Design Master in the set might partition your replica set into two irreconcilable sets and prevent any further synchronization of data.</span></span>

<span data-ttu-id="c24e8-p104">如果决定使某个副本成为副本集的新设计母版，请在该副本中设置 **DesignMasterID** 属性之前，使该副本与副本集中的所有副本同步。要使副本成为设计母版，该副本必须以独占模式打开。</span><span class="sxs-lookup"><span data-stu-id="c24e8-p104">If you decide to make a replica the new Design Master for the set, synchronize it with all the replicas in the replica set before setting the **DesignMasterID** property in the replica. The replica must be open in exclusive mode in order to make it the Design Master.</span></span>

<span data-ttu-id="c24e8-117">如果要使一个指定为只读的副本成为设计母版，则应该将目标副本设置为可读写；旧的设计母版同样应保持为可读写。</span><span class="sxs-lookup"><span data-stu-id="c24e8-117">If you make a replica that is designated read-only into the Design Master, the target replica is made read/write; the old Design Master also remains read/write.</span></span>

<span data-ttu-id="c24e8-118">**DesignMasterID** 属性设置存储在 MSysRepInfo 系统表中。</span><span class="sxs-lookup"><span data-stu-id="c24e8-118">The **DesignMasterID** property setting is stored in the MSysRepInfo system table.</span></span>

## <a name="example"></a><span data-ttu-id="c24e8-119">示例</span><span class="sxs-lookup"><span data-stu-id="c24e8-119">Example</span></span>

<span data-ttu-id="c24e8-p105">以下示例将 **DesignMasterID** 属性设置为另一个数据库的 **ReplicaID** 属性设置，从而使该数据库成为副本集中的设计母版。新旧设计母版将进行同步以更新设计更改。若要使该代码工作，必须创建一个设计母版和副本，再根据需要包括其名称和路径，然后从数据库（而不是新的或旧的设计母版）运行该代码。</span><span class="sxs-lookup"><span data-stu-id="c24e8-p105">This example sets the **DesignMasterID** property to the **ReplicaID** property setting of another database, making that database the Design Master in the replica set. The old and new Design Masters are synchronized to update the design change. For this code to work, you must create a Design Master and replica, include their names and paths as appropriate, and run this code from a database other than the old or new Design Master.</span></span>

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

