---
title: Index.Clustered 属性 (DAO)
TOCTitle: Clustered Property
ms:assetid: dd0876a9-b7fe-c8c8-e675-5ed758ce5bd3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835375(v=office.15)
ms:contentKeyID: 48548149
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052930
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4e7bd39d3329c83ec2a26fbef11e3a3b4e51e760
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921299"
---
# <a name="indexclustered-property-dao"></a><span data-ttu-id="5407a-102">Index.Clustered 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="5407a-102">Index.Clustered property (DAO)</span></span>


<span data-ttu-id="5407a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5407a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="5407a-p101">设置或返回一个值，该值指示某个 **Index** 对象是否代表某个表的聚簇索引（仅适用于 Microsoft Access 工作区）。可读写 **Boolean**。</span><span class="sxs-lookup"><span data-stu-id="5407a-p101">Sets or returns a value that indicates whether an **Index** object represents a clustered index for a table (Microsoft Access workspaces only). Read/write **Boolean**.</span></span>

## <a name="syntax"></a><span data-ttu-id="5407a-106">语法</span><span class="sxs-lookup"><span data-stu-id="5407a-106">Syntax</span></span>

<span data-ttu-id="5407a-107">*表达式*。群集</span><span class="sxs-lookup"><span data-stu-id="5407a-107">*expression* .Clustered</span></span>

<span data-ttu-id="5407a-108">*表达式*返回一个**Index**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="5407a-108">*expression* An expression that returns a **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5407a-109">注解</span><span class="sxs-lookup"><span data-stu-id="5407a-109">Remarks</span></span>

<span data-ttu-id="5407a-110">如果 **Index** 对象代表聚簇索引，则设置或返回值为 Boolean 数据类型 **True**。</span><span class="sxs-lookup"><span data-stu-id="5407a-110">The setting or return value is a Boolean data type that is **True** if the **Index** object represents a clustered index.</span></span>

<span data-ttu-id="5407a-p102">某些 IISAM 桌面数据库格式使用聚簇索引。聚簇索引包含一个或多个组合在一起的非键字段，这些字段可以按预定义的顺序排列表中的所有记录。聚簇索引可以对索引值可能不唯一的表中的记录提供高效访问。</span><span class="sxs-lookup"><span data-stu-id="5407a-p102">Some IISAM desktop database formats use clustered indexes. A clustered index consists of one or more nonkey fields that, taken together, arrange all records in a table in a predefined order. A clustered index provides efficient access to records in a table in which the index values may not be unique.</span></span>

<span data-ttu-id="5407a-114">**Clustered** 属性对于尚未追加到集合的新 **Index** 对象是可读写的，而对于 **Indexes** 集合中的现有 **Index** 对象是只读的。</span><span class="sxs-lookup"><span data-stu-id="5407a-114">The **Clustered** property is read/write for a new **Index** object not yet appended to a collection and read-only for an existing **Index** object in an **Indexes** collection.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="5407a-115">Microsoft Access 数据库引擎数据库将忽略 <STRONG>Clustered</STRONG> 属性，这是因为 Microsoft Access 数据库引擎不支持聚簇索引。</span><span class="sxs-lookup"><span data-stu-id="5407a-115">Microsoft Access database engine databases ignore the <STRONG>Clustered</STRONG> property because the Microsoft Access database engine doesn't support clustered indexes.</span></span></P>
> <LI>
> <P><span data-ttu-id="5407a-116">对于 ODBC 数据源， <STRONG>Clustered</STRONG> 属性始终返回 <STRONG>False</STRONG>；它不检测 ODBC 数据源是否具有聚簇索引。</span><span class="sxs-lookup"><span data-stu-id="5407a-116">For ODBC data sources the <STRONG>Clustered</STRONG> property always returns <STRONG>False</STRONG>; it does not detect whether or not the ODBC data source has a clustered index.</span></span></P></LI></UL>


