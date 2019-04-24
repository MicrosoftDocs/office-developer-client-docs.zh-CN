---
title: 将 ADO 与 ADO MD 结合使用
TOCTitle: Using ADO with ADO MD
ms:assetid: 93d1d270-b8d0-4489-d441-11a61887291c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249655(v=office.15)
ms:contentKeyID: 48546405
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 80c87f57a96f98de704e3cfa9b7689a522e4a7af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312745"
---
# <a name="using-ado-with-ado-md"></a><span data-ttu-id="43b9f-102">将 ADO 与 ADO MD 结合使用</span><span class="sxs-lookup"><span data-stu-id="43b9f-102">Using ADO with ADO MD</span></span>


<span data-ttu-id="43b9f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="43b9f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="43b9f-p101">ADO 和 ADO MD 是两种既相关又独立的对象模型。ADO 提供的对象用于连接数据源、执行命令、检索表格式数据和表格式架构元数据，以及查看提供程序错误信息。ADO MD 提供的对象则用于检索多维数据以及查看多维架构元数据。</span><span class="sxs-lookup"><span data-stu-id="43b9f-p101">ADO and ADO MD are related but separate object models. ADO provides objects for connecting to data sources, executing commands, retrieving tabular data and schema metadata in a tabular format, and viewing provider error information. ADO MD provides objects for retrieving multidimensional data and viewing multidimensional schema metadata.</span></span>

<span data-ttu-id="43b9f-p102">使用 MDP 时，您可以选择将 ADO、ADO MD 或者两者同时用于您的应用程序。通过在项目中引用这两个库，您将可以使用 MDP 提供的全部功能。</span><span class="sxs-lookup"><span data-stu-id="43b9f-p102">When working with an MDP you may choose to use ADO, ADO MD, or both with your application. By referencing both libraries within your project, you will have full access to the functionality provided by your MDP.</span></span>

<span data-ttu-id="43b9f-109">多维数据集的平面表格视图通常对用户很有用。</span><span class="sxs-lookup"><span data-stu-id="43b9f-109">It is often useful for consumers to get a flattened, tabular view of a multidimensional dataset.</span></span> <span data-ttu-id="43b9f-110">使用 ADO [Recordset](recordset-object-ado.md) 对象可做到这一点。</span><span class="sxs-lookup"><span data-stu-id="43b9f-110">You can do this by using the ADO [Recordset](recordset-object-ado.md) object.</span></span> <span data-ttu-id="43b9f-111">此时，请将 [Cellset](cellset-object-ado-md.md) 的源指定为 ***Recordset*** 的 Open 方法的 **[Source](open-method-ado-recordset.md)** 参数，而不是 ADO MD **Cellset** 的源。</span><span class="sxs-lookup"><span data-stu-id="43b9f-111">Specify the source for your [Cellset](cellset-object-ado-md.md) as the ***Source*** parameter for the [Open](open-method-ado-recordset.md) method of a **Recordset**, rather than as the source for an ADO MD **Cellset**.</span></span>

<span data-ttu-id="43b9f-112">以表格式视图而不是作为对象层次结构来查看架构元数据，可能也很有用。</span><span class="sxs-lookup"><span data-stu-id="43b9f-112">It may also be useful to view the schema metadata in a tabular view rather than as a hierarchy of objects.</span></span> <span data-ttu-id="43b9f-113">ADO [Connection](connection-object-ado.md) 对象的 [OpenSchema](openschema-method-ado.md) 方法使用户可以打开包含架构信息的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="43b9f-113">The ADO [OpenSchema](openschema-method-ado.md) method on the [Connection](connection-object-ado.md) object allows the user to open a **Recordset** containing schema information.</span></span> <span data-ttu-id="43b9f-114">***OpenSchema*** 方法的 **QueryType** 参数有多个专门与 MDP 关联的 [SchemaEnum](schemaenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="43b9f-114">The ***QueryType*** parameter of the **OpenSchema** method has several [SchemaEnum](schemaenum.md) values that relate specifically to MDPs.</span></span> <span data-ttu-id="43b9f-115">这些值是：</span><span class="sxs-lookup"><span data-stu-id="43b9f-115">These values are:</span></span>

  - <span data-ttu-id="43b9f-116">**adSchemaCubes**</span><span class="sxs-lookup"><span data-stu-id="43b9f-116">**adSchemaCubes**</span></span>

  - <span data-ttu-id="43b9f-117">**adSchemaDimensions**</span><span class="sxs-lookup"><span data-stu-id="43b9f-117">**adSchemaDimensions**</span></span>

  - <span data-ttu-id="43b9f-118">**adSchemaHierarchies**</span><span class="sxs-lookup"><span data-stu-id="43b9f-118">**adSchemaHierarchies**</span></span>

  - <span data-ttu-id="43b9f-119">**adSchemaLevels**</span><span class="sxs-lookup"><span data-stu-id="43b9f-119">**adSchemaLevels**</span></span>

  - <span data-ttu-id="43b9f-120">**adSchemaMeasures**</span><span class="sxs-lookup"><span data-stu-id="43b9f-120">**adSchemaMeasures**</span></span>

  - <span data-ttu-id="43b9f-121">**adSchemaMembers**</span><span class="sxs-lookup"><span data-stu-id="43b9f-121">**adSchemaMembers**</span></span>

<span data-ttu-id="43b9f-p105">若要将 ADO 枚举值与 ADO MD 属性或方法一起使用，您的项目必须同时引用 ADO 和 ADO MD 库。例如，可将 ADO **adState** 枚举值与 ADO MD [State](state-property-ado-md.md) 属性一起使用。有关如何建立库引用的更多信息，请参阅您的开发工具文档。</span><span class="sxs-lookup"><span data-stu-id="43b9f-p105">To use ADO enum values with ADO MD properties or methods, your project must reference both the ADO and ADO MD libraries. For example, you can use the ADO **adState** enum values with the ADO MD [State](state-property-ado-md.md) property. For more information about establishing references to libraries, see the documentation of your development tool.</span></span>

<span data-ttu-id="43b9f-125">有关 ADO 对象和方法的更多信息，请参阅 [ADO API 参考](ado-api-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="43b9f-125">For more information about the ADO objects and methods, see the [ADO API Reference](ado-api-reference.md).</span></span>

