---
title: ActiveConnection 属性 (ADO)
TOCTitle: ActiveConnection property (ADO)
ms:assetid: 5501b2d7-b62c-5fff-1edd-2b7efb3f8c4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249281(v=office.15)
ms:contentKeyID: 48544918
ms.date: 10/17/2018
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231115
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 037ae753f427c42f147972170dbb2e645b260623
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703200"
---
# <a name="activeconnection-property-ado"></a><span data-ttu-id="2849b-102">ActiveConnection 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2849b-102">ActiveConnection property (ADO)</span></span>

<span data-ttu-id="2849b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2849b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2849b-104">指示指定的 [Command](connection-object-ado.md)、[Recordset](command-object-ado.md) 或 [Record](recordset-object-ado.md) 对象当前属于哪个 [Connection](record-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="2849b-104">Indicates to which [Connection](connection-object-ado.md) object the specified [Command](command-object-ado.md), [Recordset](recordset-object-ado.md), or [Record](record-object-ado.md) object currently belongs.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="2849b-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="2849b-105">Settings and return values</span></span>

<span data-ttu-id="2849b-p101">如果某个连接处于关闭状态，则设置或返回一个 **String** 值，其中包含该连接的定义；如果某个连接处于打开状态，则设置或返回一个 **Variant** ，其中包含当前的 **Connection** 对象。默认值为一个空对象引用。请参阅 [ConnectionString](connectionstring-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="2849b-p101">Sets or returns a **String** value that contains a definition for a connection if the connection is closed, or a **Variant** containing the current **Connection** object if the connection is open. Default is a null object reference. See the [ConnectionString](connectionstring-property-ado.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="2849b-109">备注</span><span class="sxs-lookup"><span data-stu-id="2849b-109">Remarks</span></span>

<span data-ttu-id="2849b-110">使用 **ActiveConnection** 属性可以确定 **Connection** 对象，通过该对象将执行指定的 **Command** 对象或打开指定的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="2849b-110">Use the **ActiveConnection** property to determine the **Connection** object over which the specified **Command** object will execute or the specified **Recordset** will be opened.</span></span>

### <a name="command"></a><span data-ttu-id="2849b-111">Command</span><span class="sxs-lookup"><span data-stu-id="2849b-111">Command</span></span>

<span data-ttu-id="2849b-112">对于 **Command** 对象， **ActiveConnection** 属性为读/写属性。</span><span class="sxs-lookup"><span data-stu-id="2849b-112">For **Command** objects, the **ActiveConnection** property is read/write.</span></span>

<span data-ttu-id="2849b-113">如果在将此属性设置为打开的 [Connection](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) 对象或有效的连接字符串前，尝试对 **Command** 对象调用 **Execute** 方法，则将发生错误。</span><span class="sxs-lookup"><span data-stu-id="2849b-113">If you attempt to call the [Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command) method on a **Command** object before setting this property to an open **Connection** object or valid connection string, an error occurs.</span></span>

<span data-ttu-id="2849b-114">**Microsoft Visual Basic**： 将**ActiveConnection**属性设置为*Nothing*解除关联从当前**连接**的**Command**对象和导致版本上数据的任何相关的资源提供程序源。</span><span class="sxs-lookup"><span data-stu-id="2849b-114">**Microsoft Visual Basic**: Setting the **ActiveConnection** property to *Nothing* disassociates the **Command** object from the current **Connection** and causes the provider to release any associated resources on the data source.</span></span> <span data-ttu-id="2849b-115">然后可以将 **Command** 对象与同一个或另一个 **Connection** 对象关联。</span><span class="sxs-lookup"><span data-stu-id="2849b-115">You can then associate the **Command** object with the same or another **Connection** object.</span></span> <span data-ttu-id="2849b-116">某些提供程序允许您更改的属性设置从一个**连接**到另一个，而不必先将属性设置为*Nothing*。</span><span class="sxs-lookup"><span data-stu-id="2849b-116">Some providers allow you to change the property setting from one **Connection** to another, without having to first set the property to *Nothing*.</span></span>

<span data-ttu-id="2849b-117">如果将**Command**对象的[Parameters](parameters-collection-ado.md)集合包含由提供商的参数，如果您将**ActiveConnection**属性设置为*Nothing*或另一个**Connection**对象清除集合。</span><span class="sxs-lookup"><span data-stu-id="2849b-117">If the [Parameters](parameters-collection-ado.md) collection of the **Command** object contains parameters supplied by the provider, the collection is cleared if you set the **ActiveConnection** property to *Nothing* or to another **Connection** object.</span></span> <span data-ttu-id="2849b-118">如果您手动创建[Parameter](parameter-object-ado.md)对象，并使用它们来填充**Command**对象的**Parameters**集合，设置**ActiveConnection**属性设为*Nothing*或另一个**Connection**对象离开**Parameters**集合保持不变。</span><span class="sxs-lookup"><span data-stu-id="2849b-118">If you manually create [Parameter](parameter-object-ado.md) objects and use them to fill the **Parameters** collection of the **Command** object, setting the **ActiveConnection** property to *Nothing* or to another **Connection** object leaves the **Parameters** collection intact.</span></span>

<span data-ttu-id="2849b-p104">如果将与 **Command** 对象关联的 **Connection** 对象关闭，则会将 **ActiveConnection** 属性设置为 *Nothing*。将此属性设置为已关闭的 **Connection** 对象将生成错误。</span><span class="sxs-lookup"><span data-stu-id="2849b-p104">Closing the **Connection** object with which a **Command** object is associated sets the **ActiveConnection** property to *Nothing*. Setting this property to a closed **Connection** object generates an error.</span></span>

### <a name="recordset"></a><span data-ttu-id="2849b-121">Recordset</span><span class="sxs-lookup"><span data-stu-id="2849b-121">Recordset</span></span>

<span data-ttu-id="2849b-p105">对于打开的 **Recordset** 对象或其 **Source** 属性设置为有效 [Command](source-property-ado-recordset.md) 对象的 **Recordset** 对象， **ActiveConnection** 属性为只读属性。否则，该属性为读/写属性。</span><span class="sxs-lookup"><span data-stu-id="2849b-p105">For open **Recordset** objects or for **Recordset** objects whose [Source](source-property-ado-recordset.md) property is set to a valid **Command** object, the **ActiveConnection** property is read-only. Otherwise, it is read/write.</span></span>

<span data-ttu-id="2849b-p106">可以将此属性设置为有效的 **Connection** 对象或有效的连接字符串。在这种情况下，提供程序将使用此定义创建一个新 **Connection** 对象，并打开该连接。此外，提供程序还可能将此属性设置为新 **Connection** 对象，以便提供访问 **Connection** 对象获得扩展错误消息或执行其他命令的方式。</span><span class="sxs-lookup"><span data-stu-id="2849b-p106">You can set this property to a valid **Connection** object or to a valid connection string. In this case, the provider creates a new **Connection** object using this definition and opens the connection. Additionally, the provider may set this property to the new **Connection** object to give you a way to access the **Connection** object for extended error information or to execute other commands.</span></span>

<span data-ttu-id="2849b-127">如果您使用[Open](open-method-ado-recordset.md)方法的*ActiveConnection*参数打开**Recordset**对象， **ActiveConnection**属性将继承该参数的值。</span><span class="sxs-lookup"><span data-stu-id="2849b-127">If you use the *ActiveConnection* argument of the [Open](open-method-ado-recordset.md) method to open a **Recordset** object, the **ActiveConnection** property will inherit the value of the argument.</span></span>

<span data-ttu-id="2849b-128">如果将 **Recordset** 对象的 **Source** 属性设置为有效的 **Command** 对象变量， **Recordset** 的 **ActiveConnection** 属性将继承 **Command** 对象的 **ActiveConnection** 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="2849b-128">If you set the **Source** property of the **Recordset** object to a valid **Command** object variable, the **ActiveConnection** property of the **Recordset** inherits the setting of the **Command** object's **ActiveConnection** property.</span></span>

<span data-ttu-id="2849b-129">**远程数据服务用法**： 当客户端 Recordset 对象上使用，此属性可以仅对连接字符串或设置 （在 Microsoft Visual Basic 或 Visual Basic Scripting Edition） 为*Nothing*。</span><span class="sxs-lookup"><span data-stu-id="2849b-129">**Remote Data Service Usage**: When used on a client-side Recordset object, this property can be set only to a connection string or (in Microsoft Visual Basic or Visual Basic, Scripting Edition) to *Nothing*.</span></span>

### <a name="record"></a><span data-ttu-id="2849b-130">Record</span><span class="sxs-lookup"><span data-stu-id="2849b-130">Record</span></span>

<span data-ttu-id="2849b-p107">当 **Record** 对象关闭时此属性为可读/写属性，可以包含连接字符串或对打开的 **Connection** 对象的引用。当 **Record** 对象打开时，此属性为只读属性且包含对打开的 **Connection** 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2849b-p107">This property is read/write when the **Record** object is closed, and may contain a connection string or reference to an open **Connection** object. This property is read-only when the **Record** object is open, and contains a reference to an open **Connection** object.</span></span>

<span data-ttu-id="2849b-133">当从 URL 打开 **Record** 对象时，会隐式地创建一个 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="2849b-133">A **Connection** object is created implicitly when the **Record** object is opened from a URL.</span></span> <span data-ttu-id="2849b-134">通过将该 **Connection** 对象分配给此属性，或在 **Open** 方法调用中使用 **Connection** 对象作为参数，可以使用现有的已打开的 **Connection** 对象打开 [Record](open-method-ado-record.md) 。</span><span class="sxs-lookup"><span data-stu-id="2849b-134">Open the **Record** with an existing, open **Connection** object by assigning the **Connection** object to this property, or using the **Connection** object as a parameter in the [Open](open-method-ado-record.md) method call.</span></span> <span data-ttu-id="2849b-135">如果从现有的**Record**或[Recordset](recordset-object-ado.md)打开**Record** ，则自动相关联的**Record**或**Recordset**对象的**Connection**对象。</span><span class="sxs-lookup"><span data-stu-id="2849b-135">If the **Record** is opened from an existing **Record** or [Recordset](recordset-object-ado.md), it is automatically associated with that **Record** or **Recordset** object's **Connection** object.</span></span>

> [!NOTE]
> <span data-ttu-id="2849b-136">[!注释] 使用 HTTP 架构的 URL 将自动调用 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。</span><span class="sxs-lookup"><span data-stu-id="2849b-136">URLs using the http scheme will automatically invoke the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md).</span></span> <span data-ttu-id="2849b-137">有关详细信息，请参阅[绝对和相对 Url](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="2849b-137">For more information, see [Absolute and relative URLs](absolute-and-relative-urls.md).</span></span>



