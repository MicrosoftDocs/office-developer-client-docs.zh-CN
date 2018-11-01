---
title: OpenSchema 方法 (ADO)
TOCTitle: OpenSchema Method (ADO)
ms:assetid: 57771163-a14e-207a-2942-849acb79a9a1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249294(v=office.15)
ms:contentKeyID: 48544970
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 36f82510c4dd0004aa89b3f79ac0049cc2193ed3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877665"
---
# <a name="openschema-method-ado"></a><span data-ttu-id="0698f-102">OpenSchema 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="0698f-102">OpenSchema Method (ADO)</span></span>


<span data-ttu-id="0698f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0698f-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="0698f-104">用于从提供程序获取数据库架构信息。</span><span class="sxs-lookup"><span data-stu-id="0698f-104">Obtains database schema information from the provider .</span></span>

## <a name="syntax"></a><span data-ttu-id="0698f-105">语法</span><span class="sxs-lookup"><span data-stu-id="0698f-105">Syntax</span></span>

<span data-ttu-id="0698f-106">**设置 \*\*\* recordset* = *连接*。OpenSchema (* QueryType *，*条件\*， *SchemaID*)</span><span class="sxs-lookup"><span data-stu-id="0698f-106">**Set\*\*\*recordset* = *connection*.OpenSchema (* QueryType\*, *Criteria*, *SchemaID*)</span></span>

## <a name="return-values"></a><span data-ttu-id="0698f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="0698f-107">Return values</span></span>

<span data-ttu-id="0698f-108">返回包含架构信息的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="0698f-108">Returns a [Recordset](recordset-object-ado.md) object that contains schema information.</span></span> <span data-ttu-id="0698f-109">**Recordset** 将作为只读的静态游标打开。</span><span class="sxs-lookup"><span data-stu-id="0698f-109">The **Recordset** will be opened as a read-only, static cursor .</span></span> <span data-ttu-id="0698f-110">*QueryType*确定**Recordset**中显示的列。</span><span class="sxs-lookup"><span data-stu-id="0698f-110">The *QueryType* determines what columns appear in the **Recordset**.</span></span>

## <a name="parameters"></a><span data-ttu-id="0698f-111">参数</span><span class="sxs-lookup"><span data-stu-id="0698f-111">Parameters</span></span>

  - <span data-ttu-id="0698f-112">*QueryType*</span><span class="sxs-lookup"><span data-stu-id="0698f-112">*QueryType*</span></span>

  - <span data-ttu-id="0698f-113">任何 [SchemaEnum](schemaenum.md) 值，表示要运行的架构查询类型。</span><span class="sxs-lookup"><span data-stu-id="0698f-113">Any [SchemaEnum](schemaenum.md) value that represents the type of schema query to run.</span></span>

  - <span data-ttu-id="0698f-114">*Criteria*</span><span class="sxs-lookup"><span data-stu-id="0698f-114">*Criteria*</span></span>

  - <span data-ttu-id="0698f-115">可选。</span><span class="sxs-lookup"><span data-stu-id="0698f-115">Optional.</span></span> <span data-ttu-id="0698f-116">每个*QueryType*选项，如**SchemaEnum**中列出的查询约束数组。</span><span class="sxs-lookup"><span data-stu-id="0698f-116">An array of query constraints for each *QueryType* option, as listed in **SchemaEnum**.</span></span>

  - <span data-ttu-id="0698f-117">*SchemaID*</span><span class="sxs-lookup"><span data-stu-id="0698f-117">*SchemaID*</span></span>

  - <span data-ttu-id="0698f-118">提供程序架构查询的 GUID 不是由 OLE DB 规范定义的。</span><span class="sxs-lookup"><span data-stu-id="0698f-118">The GUID for a provider-schema query not defined by the OLE DB specification.</span></span> <span data-ttu-id="0698f-119">此参数是必需的如果*QueryType*设置为**adSchemaProviderSpecific**;否则，它将不使用。</span><span class="sxs-lookup"><span data-stu-id="0698f-119">This parameter is required if *QueryType* is set to **adSchemaProviderSpecific**; otherwise, it is not used.</span></span>

## <a name="remarks"></a><span data-ttu-id="0698f-120">备注</span><span class="sxs-lookup"><span data-stu-id="0698f-120">Remarks</span></span>

<span data-ttu-id="0698f-121">**OpenSchema** 方法返回有关数据源的自描述信息，例如数据源中有哪些表、表中有哪些列以及支持哪些数据类型。</span><span class="sxs-lookup"><span data-stu-id="0698f-121">The **OpenSchema** method returns self-descriptive information about the data source, such as what tables are in the data source, the columns in the tables, and the data types supported.</span></span>

<span data-ttu-id="0698f-122">*QueryType*参数是表示的列 （架构） 返回的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0698f-122">The *QueryType* argument is a GUID that indicates the columns (schemas) returned.</span></span> <span data-ttu-id="0698f-123">OLE DB 规范具有架构的完整列表。</span><span class="sxs-lookup"><span data-stu-id="0698f-123">The OLE DB specification has a full list of schemas.</span></span>

<span data-ttu-id="0698f-p105">*Criteria* 参数限制架构查询的结果。*Criteria* 指定生成的 **Recordset** 中相应的列子集（称为*约束列*）中必须出现的值数组。</span><span class="sxs-lookup"><span data-stu-id="0698f-p105">The *Criteria* argument limits the results of a schema query. *Criteria* specifies an array of values that must occur in a corresponding subset of columns, called *constraint columns*, in the resulting **Recordset**.</span></span>

<span data-ttu-id="0698f-126">如果提供程序定义自己的非标准架构查询外部上面列出的那些常量**adSchemaProviderSpecific**用于*QueryType*参数。</span><span class="sxs-lookup"><span data-stu-id="0698f-126">The constant **adSchemaProviderSpecific** is used for the *QueryType* argument if the provider defines its own nonstandard schema queries outside those listed above.</span></span> <span data-ttu-id="0698f-127">使用此常量时， *SchemaID*参数必须通过执行架构查询的 GUID。</span><span class="sxs-lookup"><span data-stu-id="0698f-127">When this constant is used, the *SchemaID* argument is required to pass the GUID of the schema query to execute.</span></span> <span data-ttu-id="0698f-128">如果设置为**adSchemaProviderSpecific** *QueryType*但未提供*SchemaID* ，将导致错误。</span><span class="sxs-lookup"><span data-stu-id="0698f-128">If *QueryType* is set to **adSchemaProviderSpecific** but *SchemaID* is not provided, an error will result.</span></span>

<span data-ttu-id="0698f-129">提供程序不需要支持所有 OLE DB 标准架构查询。</span><span class="sxs-lookup"><span data-stu-id="0698f-129">Providers are not required to support all of the OLE DB standard schema queries.</span></span> <span data-ttu-id="0698f-130">具体来说，只有 **adSchemaTables** 、 **adSchemaColumns** 和 **adSchemaProviderTypes** 是 OLE DB 规范所必需的。</span><span class="sxs-lookup"><span data-stu-id="0698f-130">Specifically, only **adSchemaTables**, **adSchemaColumns**, and **adSchemaProviderTypes** are required by the OLE DB specification.</span></span> <span data-ttu-id="0698f-131">但是，提供程序不需要支持这些架构查询上面列出的*条件*约束。</span><span class="sxs-lookup"><span data-stu-id="0698f-131">However, the provider is not required to support the *Criteria* constraints listed above for those schema queries.</span></span>

<span data-ttu-id="0698f-132">**远程数据服务用法\*\*\*\*OpenSchema**方法不可用在客户端[Connection](connection-object-ado.md)对象上。</span><span class="sxs-lookup"><span data-stu-id="0698f-132">**Remote Data Service Usage**The **OpenSchema** method is not available on a client-side [Connection](connection-object-ado.md) object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="0698f-p108">在 Visual Basic 中，从 <STRONG>Connection</STRONG> 对象的 <STRONG>OpenSchema</STRONG> 方法返回的 <STRONG>Recordset</STRONG> 中具有四字节无符号整数 (DBTYPE UI4) 的列不能与其他变量进行比较。有关 OLE DB 数据类型的详细信息，请参阅<EM>《Microsoft OLE DB 程序员参考》</EM>的第 13 章和附录 A。</span><span class="sxs-lookup"><span data-stu-id="0698f-p108">In Visual Basic, columns that have a four-byte unsigned integer (DBTYPE UI4) in the <STRONG>Recordset</STRONG> returned from the <STRONG>OpenSchema</STRONG> method on the <STRONG>Connection</STRONG> object cannot be compared to other variables. For more information about OLE DB data types, see Chapter 13 and Appendix A of the <EM>Microsoft OLE DB Programmer's Reference</EM>.</span></span></P>


