---
title: Database.MakeReplica 方法 (DAO)
TOCTitle: MakeReplica Method
ms:assetid: b6bf4982-0804-12ce-849f-d2b4ac2e48a5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822413(v=office.15)
ms:contentKeyID: 48547286
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053371
f1_categories:
- Office.Version=v15
ms.openlocfilehash: a47709d1be3eab66f849e076c5756d5081d28fc8
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930229"
---
# <a name="databasemakereplica-method-dao"></a><span data-ttu-id="4a064-102">Database.MakeReplica 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4a064-102">Database.MakeReplica method (DAO)</span></span>

<span data-ttu-id="4a064-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4a064-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4a064-104">根据另一个数据库副本制作一个新的副本（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="4a064-104">Makes a new replica from another database replica (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="4a064-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a064-105">Syntax</span></span>

<span data-ttu-id="4a064-106">*表达式*。MakeReplica （***路径名***，在***说明***中，***选项***）</span><span class="sxs-lookup"><span data-stu-id="4a064-106">*expression* .MakeReplica(***PathName***, ***Description***, ***Options***)</span></span>

<span data-ttu-id="4a064-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4a064-107">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="4a064-108">参数</span><span class="sxs-lookup"><span data-stu-id="4a064-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4a064-109">名称</span><span class="sxs-lookup"><span data-stu-id="4a064-109">Name</span></span></p></th>
<th><p><span data-ttu-id="4a064-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="4a064-110">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="4a064-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="4a064-111">Data Type</span></span></p></th>
<th><p><span data-ttu-id="4a064-112">说明</span><span class="sxs-lookup"><span data-stu-id="4a064-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a064-113">PathName</span><span class="sxs-lookup"><span data-stu-id="4a064-113">PathName</span></span></p></td>
<td><p><span data-ttu-id="4a064-114">必需</span><span class="sxs-lookup"><span data-stu-id="4a064-114">Required</span></span></p></td>
<td><p><span data-ttu-id="4a064-115"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="4a064-115"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="4a064-p101">新副本的路径和文件名。如果 replica 是一个现有的文件名，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="4a064-p101">The path and file name of the new replica. If replica is an existing file name, then an error occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a064-118">说明</span><span class="sxs-lookup"><span data-stu-id="4a064-118">Description</span></span></p></td>
<td><p><span data-ttu-id="4a064-119">必需</span><span class="sxs-lookup"><span data-stu-id="4a064-119">Required</span></span></p></td>
<td><p><span data-ttu-id="4a064-120"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="4a064-120"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="4a064-121">一个 <strong>String</strong>，用于描述所创建的副本</span><span class="sxs-lookup"><span data-stu-id="4a064-121">A <strong>String</strong> that describes the replica that you are creating</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a064-122">选项</span><span class="sxs-lookup"><span data-stu-id="4a064-122">Options</span></span></p></td>
<td><p><span data-ttu-id="4a064-123">可选</span><span class="sxs-lookup"><span data-stu-id="4a064-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="4a064-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="4a064-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="4a064-125">一个<strong><a href="replicatypeenum-enumeration-dao.md">ReplicaTypeEnum</a></strong>常量，指定要创建的副本的特征。</span><span class="sxs-lookup"><span data-stu-id="4a064-125">A <strong><a href="replicatypeenum-enumeration-dao.md">ReplicaTypeEnum</a></strong> constant that specifies characteristics of the replica you are creating.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4a064-126">注解</span><span class="sxs-lookup"><span data-stu-id="4a064-126">Remarks</span></span>

<span data-ttu-id="4a064-127">新建部分副本的所有 **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** 属性都将设置为 **False**，表示不会将任何数据放入表中。</span><span class="sxs-lookup"><span data-stu-id="4a064-127">A newly created partial replica will have all **[ReplicaFilter](tabledef-replicafilter-property-dao.md)** properties set to **False**, meaning that no data will be in the tables.</span></span>

## <a name="example"></a><span data-ttu-id="4a064-128">示例</span><span class="sxs-lookup"><span data-stu-id="4a064-128">Example</span></span>

<span data-ttu-id="4a064-129">此函数使用 **MakeReplica** 方法创建现有设计母版的附加副本。</span><span class="sxs-lookup"><span data-stu-id="4a064-129">This function uses the **MakeReplica** method to create an additional replica of an existing Design Master.</span></span> <span data-ttu-id="4a064-130">IntOptions 参数可以是组合的常量**dbRepMakeReadOnly**和**dbRepMakePartial**，也可以是 0。</span><span class="sxs-lookup"><span data-stu-id="4a064-130">The intOptions argument can be a combination of the constants **dbRepMakeReadOnly** and **dbRepMakePartial**, or it can be 0.</span></span> <span data-ttu-id="4a064-131">例如，若要创建只读的部分副本，您应传递值**dbRepMakeReadOnly** + **dbRepMakePartial**作为 intOptions 的值。</span><span class="sxs-lookup"><span data-stu-id="4a064-131">For example, to create a read-only partial replica, you should pass the value **dbRepMakeReadOnly** + **dbRepMakePartial** as the value of intOptions.</span></span>

```vb 
Function MakeAdditionalReplica(strReplicableDB As _ 
 String, strNewReplica As String, intOptions As _ 
 Integer) As Integer 
 
 Dim dbsTemp As Database 
 On Error GoTo ErrorHandler 
 
 Set dbsTemp = OpenDatabase(strReplicableDB) 
 
 ' If no options are passed to 
 ' MakeAdditionalReplica, omit the 
 ' options argument, which defaults to 
 ' a full, read/write replica. Otherwise, 
 ' use the value of intOptions. 
 
 If intOptions = 0 Then 
 dbsTemp.MakeReplica strNewReplica, _ 
 "Replica of " & strReplicableDB 
 Else 
 dbsTemp.MakeReplica strNewReplica, _ 
 "Replica of " & strReplicableDB, _ 
 intOptions 
 End If 
 
 dbsTemp.Close 
 
ErrorHandler: 
 Select Case Err 
 Case 0: 
 MakeAdditionalReplica = 0 
 Exit Function 
 Case Else: 
 MsgBox "Error " & Err & " : " & Error 
 MakeAdditionalReplica = Err 
 Exit Function 
 End Select 
 
End Function 
 
```

