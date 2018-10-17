---
title: Database.ReplicaID Property (DAO)
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
ms.openlocfilehash: ca879a3c56d23a67987d86b7fbc21421cd8db843
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465552"
---
# <a name="databasereplicaid-property-dao"></a><span data-ttu-id="0af0e-102">Database.ReplicaID Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="0af0e-102">Database.ReplicaID Property (DAO)</span></span>


<span data-ttu-id="0af0e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0af0e-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="0af0e-104">返回一个 16 字节的值，该值唯一标识数据库副本（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="0af0e-104">Returns a 16-byte value that uniquely identifies a database replica (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="0af0e-105">语法</span><span class="sxs-lookup"><span data-stu-id="0af0e-105">Syntax</span></span>

<span data-ttu-id="0af0e-106">*表达式*。ReplicaID</span><span class="sxs-lookup"><span data-stu-id="0af0e-106">*expression* .ReplicaID</span></span>

<span data-ttu-id="0af0e-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0af0e-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0af0e-108">注解</span><span class="sxs-lookup"><span data-stu-id="0af0e-108">Remarks</span></span>

<span data-ttu-id="0af0e-109">返回值是一个 **GUID** 值，该值唯一标识副本或设计母版。</span><span class="sxs-lookup"><span data-stu-id="0af0e-109">The return value is a **GUID** value that uniquely identifies the replica or Design Master.</span></span>

<span data-ttu-id="0af0e-110">在您创建新副本时，Microsoft Access 数据库引擎自动生成这个值。</span><span class="sxs-lookup"><span data-stu-id="0af0e-110">The Microsoft Access database engine automatically generates this value when you create a new replica.</span></span>

<span data-ttu-id="0af0e-111">每个副本（和设计母版）的 **ReplicaID** 属性都存储在 MSysReplicas 系统表中。</span><span class="sxs-lookup"><span data-stu-id="0af0e-111">The **ReplicaID** property of each replica (and the Design Master) is stored in the MSysReplicas system table.</span></span>

## <a name="example"></a><span data-ttu-id="0af0e-112">示例</span><span class="sxs-lookup"><span data-stu-id="0af0e-112">Example</span></span>

<span data-ttu-id="0af0e-p101">以下示例从 Northwind.mdb 的设计母版生成副本，然后返回 Microsoft Access 数据库引擎自动创建的副本 **ReplicaID**。（如果您尚未创建 Northwind 数据库的设计母版，请引用 **Replicable** 属性或者将代码中数据库的名称更改为现有设计母版。）</span><span class="sxs-lookup"><span data-stu-id="0af0e-p101">This example makes a replica from the Design Master of Northwind.mdb, and then returns the replica's **ReplicaID**, which is automatically created by the Microsoft Access database engine. (If you have not yet created a Design Master of Northwind, refer to the **Replicable** property, or change the name of the database in the code to an existing Design Master.)</span></span>

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
