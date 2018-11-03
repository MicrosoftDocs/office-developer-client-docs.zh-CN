---
title: DataControl 对象 (RDS)
TOCTitle: DataControl object (RDS)
ms:assetid: ac430669-7628-696c-c036-b5d35405d788
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249801(v=office.15)
ms:contentKeyID: 48547001
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2d4b622cd65cfaf71c45ac7ae8c77bdb596ebd3a
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25937804"
---
# <a name="datacontrol-object-rds"></a><span data-ttu-id="6a7d1-102">DataControl 对象 (RDS)</span><span class="sxs-lookup"><span data-stu-id="6a7d1-102">DataControl object (RDS)</span></span>

<span data-ttu-id="6a7d1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6a7d1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6a7d1-104">将数据查询[Recordset](recordset-object-ado.md)绑定到一个或多个控件 （如文本框、 网格控件或组合框） 以便在网页上显示**Recordset**数据。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-104">Binds a data query [Recordset](recordset-object-ado.md) to one or more controls (for example, a text box, grid control, or combo box) to display the **Recordset** data on a webpage.</span></span>

## <a name="syntax"></a><span data-ttu-id="6a7d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="6a7d1-105">Syntax</span></span>

```vb
    <OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID="DataControl"
       <PARAM NAME="Connect" VALUE="DSN=DSNName;UID=usr;PWD=pw;">
       <PARAM NAME="Server" VALUE="https://awebsrvr">
       <PARAM NAME="SQL" VALUE="QueryText">
    </OBJECT>
```

## <a name="remarks"></a><span data-ttu-id="6a7d1-106">说明</span><span class="sxs-lookup"><span data-stu-id="6a7d1-106">Remarks</span></span>

<span data-ttu-id="6a7d1-107">**RDS.DataControl** 对象的类 ID 为 BD96C556-65A3-11D0-983A-00C04FC29E33。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-107">The class ID for the **RDS.DataControl** object is BD96C556-65A3-11D0-983A-00C04FC29E33.</span></span>

> [!NOTE]
> <span data-ttu-id="6a7d1-p101">[!注释] 如果出现一个错误，指示 [RDS.DataSpace](dataspace-object-rds.md) 或 **RDS.DataControl** 对象没有加载，请确保使用的类 ID 正确。这些对象的类 ID 已从版本 1.0 更改为版本 1.1。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p101">If you get an error that an [RDS.DataSpace](dataspace-object-rds.md) or **RDS.DataControl** object doesn't load, make sure you are using the correct class ID. The class IDs for these objects have changed from version 1.0 and 1.1.</span></span>

<span data-ttu-id="6a7d1-110">对于基本方案，只需设置 **RDS.DataControl** 对象的 **SQL** 、 **Connect** 和 **Server** 属性, 该对象会自动调用默认业务对象 [RDSServer.DataFactory](datafactory-object-rdsserver.md)。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-110">For a basic scenario, you need to set only the **SQL**, **Connect**, and **Server** properties of the **RDS.DataControl** object, which will automatically call the default business object, [RDSServer.DataFactory](datafactory-object-rdsserver.md).</span></span>

<span data-ttu-id="6a7d1-111">**RDS.DataControl** 中的所有属性都是可选的，因为自定义业务对象可以替代他们的功能。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-111">All the properties in the **RDS.DataControl** are optional because custom business objects can replace their functionality.</span></span>

> [!NOTE]
> <span data-ttu-id="6a7d1-112">[!注释] 如果查询多个结果，则仅返回第一个 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-112">If you query for multiple results, only the first [Recordset](recordset-object-ado.md) is returned.</span></span> <span data-ttu-id="6a7d1-113">如果需要多个结果集，可将每个结果集分配给它自己的 **DataControl** 。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-113">If multiple result sets are needed, assign each to its own **DataControl**.</span></span> 
> 
> <span data-ttu-id="6a7d1-114">针对多个结果的查询的示例可以是以下： `"Select * from Authors, Select * from Topics"`。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-114">An example of a query for multiple results could be the following: `"Select * from Authors, Select * from Topics"`.</span></span>

<span data-ttu-id="6a7d1-p103">如果在使用 **RDS.DataControl** 对象时将"DFMode=20;"添加到连接字符串中，则可以提高服务器更新数据时的性能。通过使用此设置，服务器上的 **RDSServer.DataFactory** 对象可使用资源占用量较少的模式。但是，以下功能在此配置中不可用：</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p103">Adding "DFMode=20;" to your connection string when using the **RDS.DataControl** object can improve your server's performance when updating data. With this setting, the **RDSServer.DataFactory** object on the server uses a less resource-intensive mode. However, the following features are not available in this configuration:</span></span>

  - <span data-ttu-id="6a7d1-118">使用参数化的查询。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-118">Using parameterized queries.</span></span>

  - <span data-ttu-id="6a7d1-119">调用 **Execute** 方法之前获取参数信息或列信息。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-119">Getting parameter or column information before calling the **Execute** method.</span></span>

  - <span data-ttu-id="6a7d1-120">将 **Transact Updates** 设置为 **True** 。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-120">Setting **Transact Updates** to **True**.</span></span>

  - <span data-ttu-id="6a7d1-121">获取行状态。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-121">Getting row status.</span></span>

  - <span data-ttu-id="6a7d1-122">调用 [Resync](resync-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-122">Calling the [Resync](resync-method-ado.md) method.</span></span>

  - <span data-ttu-id="6a7d1-123">通过 [Update Resync](update-resync-property-dynamic-ado.md) 属性刷新（显式或自动）。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-123">Refreshing (explicitly or automatically) via the [Update Resync](update-resync-property-dynamic-ado.md) property.</span></span>

  - <span data-ttu-id="6a7d1-124">设置 **Command** 或 [Recordset](recordset-sourcerecordset-properties-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-124">Setting **Command** or [Recordset](recordset-sourcerecordset-properties-rds.md) properties.</span></span>

  - <span data-ttu-id="6a7d1-125">使用 **adCmdTableDirect** 。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-125">Using **adCmdTableDirect**.</span></span>

<span data-ttu-id="6a7d1-p104">默认情况下， **RDS.DataControl** 对象在异步模式下运行。如果需要同步执行应用程序，可将 [ExecuteOptions](executeoptions-property-rds.md) 参数设置为等于 **adcExecSync** ，将 [FetchOptions](fetchoptions-property-rds.md) 参数设置为等于 **adcFetchUpFront** ，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p104">The **RDS.DataControl** object runs in asynchronous mode by default. If you require synchronous execution for your application, set the [ExecuteOptions](executeoptions-property-rds.md) parameter equal to **adcExecSync** and the [FetchOptions](fetchoptions-property-rds.md) parameter equal to **adcFetchUpFront**, as shown in the following example.</span></span>

```vb
    <OBJECT CLASSID="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" 
        ID="DataControl"
       <PARAM NAME="Connect" VALUE="DSN=DSNName;UID=usr;PWD=pw;">
       <PARAM NAME="Server" VALUE="https://awebsrvr">
       <PARAM NAME="SQL" VALUE="QueryText">
       <PARAM NAME="ExecuteOptions" VALUE="1">
       <PARAM NAME="FetchOptions" VALUE="1">
    </OBJECT>
```

<span data-ttu-id="6a7d1-p105">使用一个 **RDS.DataControl** 对象将一个查询的结果链接到一个或多个可视控件。例如，假设您要编写一个请求客户数据（姓名、住址、出生地、年龄和客户状态优先级）的查询。您可以使用一个 **RDS.DataControl** 对象在三个单独的文本框中显示客户姓名、年龄和地区；在一个复选框中显示客户状态优先级；并在一个网格控件中显示所有数据。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p105">Use one **RDS.DataControl** object to link the results of a single query to one or more visual controls. For example, suppose you code a query requesting customer data such as Name, Residence, Place of Birth, Age, and Priority Customer Status. You can use a single **RDS.DataControl** object to display a customer's Name, Age, and Region in three separate text boxes; Priority Customer Status in a check box; and all the data in a grid control.</span></span>

<span data-ttu-id="6a7d1-p106">使用不同的 **RDS.DataControl** 对象将多个查询的结果链接到不同的可视控件。例如，假设您使用一个查询获取有关客户的信息，使用第二个查询获取有关客户已购商品的信息。您希望在三个文本框和一个复选框中显示第一个查询的结果，在网格控件中显示第二个查询的结果。如果使用默认业务对象（**RDSServer.DataFactory**），您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p106">Use different **RDS.DataControl** objects to link the results of multiple queries to different visual controls. For example, suppose you use one query to obtain information about a customer, and a second query to obtain information about merchandise that the customer has purchased. You want to display the results of the first query in three text boxes and one check box, and the results of the second query in a grid control. If you use the default business object (**RDSServer.DataFactory**), you need to do the following:</span></span>

  - <span data-ttu-id="6a7d1-135">添加两个**rds.DataControl**对象与您的网页。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-135">Add two **RDS.DataControl** objects to your webpage.</span></span>

  - <span data-ttu-id="6a7d1-p107">编写两个查询，分别用于两个 **RDS.DataControl** 对象的每个 **SQL** 属性。一个 **RDS.DataControl** 对象将包含请求客户信息的 SQL 查询；另一个对象将包含请求客户已购商品列表的查询。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-p107">Write two queries, one for each **SQL** property of the two **RDS.DataControl** objects. One **RDS.DataControl** object will contain an SQL query requesting customer information; the second will contain a query requesting a list of merchandise the customer has purchased.</span></span>

  - <span data-ttu-id="6a7d1-138">在绑定控件各个 OBJECT 标记中，指定 DATAFLD 值以设置要在每个可视控件中显示的数据的值。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-138">In each of the bound controls' OBJECT tags, specify the DATAFLD value to set the values for the data you want to display in each visual control.</span></span>

<span data-ttu-id="6a7d1-139">Rds.**的数量没有计数限制DataControl**可以通过 OBJECT 标记单个网页上嵌入的对象。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-139">There is no count restriction on the number of **RDS.DataControl** objects that you can embed via OBJECT tags on a single webpage.</span></span>

<span data-ttu-id="6a7d1-140">当您定义**rds.DataControl**网页上对象，请使用如 1 的非零**Height**和**Width**值 （以避免包含额外空间）。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-140">When you define the **RDS.DataControl** object on a webpage, use nonzero **Height** and **Width** values such as 1 (to avoid the inclusion of extra space).</span></span>

<span data-ttu-id="6a7d1-141">远程数据服务客户端组件已作为 Internet Explorer 4.0 的一部分提供，因此不需要在 **RDS.DataControl** 对象标记中包括 CODEBASE 参数。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-141">Remote Data Service client components are already included as part of Internet Explorer 4.0; therefore, you don't need to include a CODEBASE parameter in your **RDS.DataControl** object tag.</span></span>

<span data-ttu-id="6a7d1-142">Internet Explorer 4.0 或更高版本，您可以使用 HTML 控件和 ActiveX 控件，仅当它们标记为单元模型控件绑定到数据。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-142">With Internet Explorer 4.0 or later, you can bind to data by using HTML controls and ActiveX controls only if they are marked as apartment model controls.</span></span>

<span data-ttu-id="6a7d1-143">**Microsoft Visual Basic 用户\*\*\*\*Rds.DataControl**仅在基于 web 的应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-143">**Microsoft Visual Basic Users** The **RDS.DataControl** is used only in web-based applications.</span></span> <span data-ttu-id="6a7d1-144">Visual Basic 客户端应用程序不需要它。</span><span class="sxs-lookup"><span data-stu-id="6a7d1-144">A Visual Basic client application has no need for it.</span></span>

