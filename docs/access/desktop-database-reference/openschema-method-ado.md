---
title: OpenSchema 方法 (ADO)
TOCTitle: OpenSchema method (ADO)
ms:assetid: 57771163-a14e-207a-2942-849acb79a9a1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249294(v=office.15)
ms:contentKeyID: 48544970
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 43ca69b9d761629d42138780517f8de806ed7e8c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288334"
---
# <a name="openschema-method-ado"></a><span data-ttu-id="c61d4-102">OpenSchema 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c61d4-102">OpenSchema method (ADO)</span></span>

<span data-ttu-id="c61d4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c61d4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c61d4-104">用于从提供程序获取数据库架构信息。</span><span class="sxs-lookup"><span data-stu-id="c61d4-104">Obtains database schema information from the provider .</span></span>

## <a name="syntax"></a><span data-ttu-id="c61d4-105">语法</span><span class="sxs-lookup"><span data-stu-id="c61d4-105">Syntax</span></span>

<span data-ttu-id="c61d4-106">**Set \* \* \* recordset* = *连接*。OpenSchema (* QueryType \*, *Criteria*, *SchemaID*)</span><span class="sxs-lookup"><span data-stu-id="c61d4-106">**Set\*\*\*recordset* = *connection*.OpenSchema (* QueryType\*, *Criteria*, *SchemaID*)</span></span>

## <a name="return-values"></a><span data-ttu-id="c61d4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c61d4-107">Return values</span></span>

<span data-ttu-id="c61d4-108">返回包含架构信息的 [Recordset](recordset-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="c61d4-108">Returns a [Recordset](recordset-object-ado.md) object that contains schema information.</span></span> <span data-ttu-id="c61d4-109">**Recordset** 将作为只读的静态游标打开。</span><span class="sxs-lookup"><span data-stu-id="c61d4-109">The **Recordset** will be opened as a read-only, static cursor .</span></span> <span data-ttu-id="c61d4-110">*QueryType* 确定哪些列显示在 **Recordset** 中。</span><span class="sxs-lookup"><span data-stu-id="c61d4-110">The *QueryType* determines what columns appear in the **Recordset**.</span></span>

## <a name="parameters"></a><span data-ttu-id="c61d4-111">参数</span><span class="sxs-lookup"><span data-stu-id="c61d4-111">Parameters</span></span>

|<span data-ttu-id="c61d4-112">参数</span><span class="sxs-lookup"><span data-stu-id="c61d4-112">Parameter</span></span>|<span data-ttu-id="c61d4-113">描述</span><span class="sxs-lookup"><span data-stu-id="c61d4-113">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c61d4-114">*QueryType*</span><span class="sxs-lookup"><span data-stu-id="c61d4-114">*QueryType*</span></span> |<span data-ttu-id="c61d4-115">任何 [SchemaEnum](schemaenum.md) 值，表示要运行的架构查询类型。</span><span class="sxs-lookup"><span data-stu-id="c61d4-115">Any [SchemaEnum](schemaenum.md) value that represents the type of schema query to run.</span></span>|
|<span data-ttu-id="c61d4-116">*Criteria*</span><span class="sxs-lookup"><span data-stu-id="c61d4-116">*Criteria*</span></span> |<span data-ttu-id="c61d4-117">可选。</span><span class="sxs-lookup"><span data-stu-id="c61d4-117">Optional.</span></span> <span data-ttu-id="c61d4-118">针对每个 *QueryType* 选项的查询约束的数组，如 **SchemaEnum** 中所列。</span><span class="sxs-lookup"><span data-stu-id="c61d4-118">An array of query constraints for each *QueryType* option, as listed in **SchemaEnum**.</span></span>|
|<span data-ttu-id="c61d4-119">*SchemaID*</span><span class="sxs-lookup"><span data-stu-id="c61d4-119">*SchemaID*</span></span> |<span data-ttu-id="c61d4-p103">提供程序架构查询的 GUID 不是由 OLE DB 规范定义的。如果 *QueryType* 设置为 **adSchemaProviderSpecific**，则该参数是必需的；否则，不使用该参数。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p103">The GUID for a provider-schema query not defined by the OLE DB specification. This parameter is required if *QueryType* is set to **adSchemaProviderSpecific**; otherwise, it is not used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c61d4-122">注解</span><span class="sxs-lookup"><span data-stu-id="c61d4-122">Remarks</span></span>

<span data-ttu-id="c61d4-123">**OpenSchema** 方法返回有关数据源的自描述信息，例如数据源中有哪些表、表中有哪些列以及支持哪些数据类型。</span><span class="sxs-lookup"><span data-stu-id="c61d4-123">The **OpenSchema** method returns self-descriptive information about the data source, such as what tables are in the data source, the columns in the tables, and the data types supported.</span></span>

<span data-ttu-id="c61d4-p104">*QueryType* 参数是一个 GUID，用于指示返回的列（架构）。OLE DB 规范具有架构的完整列表。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p104">The *QueryType* argument is a GUID that indicates the columns (schemas) returned. The OLE DB specification has a full list of schemas.</span></span>

<span data-ttu-id="c61d4-p105">*Criteria* 参数限制架构查询的结果。*Criteria* 指定生成的 **Recordset** 中相应的列子集（称为*约束列*）中必须出现的值数组。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p105">The *Criteria* argument limits the results of a schema query. *Criteria* specifies an array of values that must occur in a corresponding subset of columns, called *constraint columns*, in the resulting **Recordset**.</span></span>

<span data-ttu-id="c61d4-p106">如果提供程序自己定义的非标准架构查询在前面没有列出，则常量 **adSchemaProviderSpecific** 用于 *QueryType* 参数。使用该常量时，必须使用 *SchemaID* 参数才能传递要执行的架构查询的 GUID。如果 *QueryType* 设置为 **adSchemaProviderSpecific** 但未提供 *SchemaID*，将生成错误。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p106">The constant **adSchemaProviderSpecific** is used for the *QueryType* argument if the provider defines its own nonstandard schema queries outside those listed above. When this constant is used, the *SchemaID* argument is required to pass the GUID of the schema query to execute. If *QueryType* is set to **adSchemaProviderSpecific** but *SchemaID* is not provided, an error will result.</span></span>

<span data-ttu-id="c61d4-p107">提供程序不需要支持所有 OLE DB 标准架构查询。具体来说，只有 **adSchemaTables**、**adSchemaColumns** 和 **adSchemaProviderTypes** 是 OLE DB 规范所必需的。但是，对于这些架构查询，提供程序不需要支持上面所列的 *Criteria* 约束。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p107">Providers are not required to support all of the OLE DB standard schema queries. Specifically, only **adSchemaTables**, **adSchemaColumns**, and **adSchemaProviderTypes** are required by the OLE DB specification. However, the provider is not required to support the *Criteria* constraints listed above for those schema queries.</span></span>

<span data-ttu-id="c61d4-134">**远程数据服务使用情况\*\*\*\*OpenSchema**方法在客户端[Connection](connection-object-ado.md)对象上不可用。</span><span class="sxs-lookup"><span data-stu-id="c61d4-134">**Remote Data Service Usage**The **OpenSchema** method is not available on a client-side [Connection](connection-object-ado.md) object.</span></span>

> [!NOTE]
> <span data-ttu-id="c61d4-p108">在 Visual Basic 中，从 **Connection** 对象的 **OpenSchema** 方法返回的 **Recordset** 中具有四字节无符号整数 (DBTYPE UI4) 的列不能与其他变量进行比较。有关 OLE DB 数据类型的详细信息，请参阅 *《Microsoft OLE DB 程序员参考》* 的第 13 章和附录 A。</span><span class="sxs-lookup"><span data-stu-id="c61d4-p108">In Visual Basic, columns that have a four-byte unsigned integer (DBTYPE UI4) in the **Recordset** returned from the **OpenSchema** method on the **Connection** object cannot be compared to other variables. For more information about OLE DB data types, see Chapter 13 and Appendix A of the *Microsoft OLE DB Programmer's Reference*.</span></span>


