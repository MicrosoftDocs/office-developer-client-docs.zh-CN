---
title: 通讯簿数据绑定对象
TOCTitle: Address Book Data-Binding Object
ms:assetid: cf43f645-1ee1-8655-eb70-86d601e9f3f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250030(v=office.15)
ms:contentKeyID: 48547807
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7852a929f08c46feea002913a1f64d8144572080
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877553"
---
# <a name="address-book-data-binding-object"></a><span data-ttu-id="1d7f5-102">通讯簿数据绑定对象</span><span class="sxs-lookup"><span data-stu-id="1d7f5-102">Address Book Data-Binding Object</span></span>


<span data-ttu-id="1d7f5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1d7f5-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1d7f5-p101">"通讯簿"应用程序使用 [RDS.DataControl](datacontrol-object-rds.md) 对象将 SQL Server 数据库中的数据绑定到应用程序客户端 HTML 页中的可视化对象（在此例中为 DHTML 表）。事件驱动的 VBScript 程序逻辑使用 [RDS.DataControl](datacontrol-object-rds.md) 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1d7f5-p101">The Address Book application uses the [RDS.DataControl](datacontrol-object-rds.md) object to bind data from the SQL Server database to a visual object (in this case, a DHTML table) in the application's client HTML page. The event-driven VBScript program logic uses the [RDS.DataControl](datacontrol-object-rds.md) to:</span></span>

  - <span data-ttu-id="1d7f5-106">查询数据库、发送对数据库的更新和刷新数据网格。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-106">Query the database, send updates to the database, and refresh the data grid.</span></span>

  - <span data-ttu-id="1d7f5-107">允许用户在数据网格中移动到第一个、下一个、上一个或最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-107">Allow users to move to the first, next, previous, or last record in the data grid.</span></span>

<span data-ttu-id="1d7f5-108">以下代码定义了 **RDS.DataControl** 组件：</span><span class="sxs-lookup"><span data-stu-id="1d7f5-108">The following code defines the **RDS.DataControl** component:</span></span>

```vb 
 
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" 
   ID=DC1 Width=1 Height=1> 
   <PARAM NAME="SERVER" VALUE="https://<%=Request.ServerVariables("SERVER_NAME")%>"> 
   <PARAM NAME="CONNECT" VALUE="Provider=sqloledb; 
Initial Catalog=AddrBookDb;Integrated Security=SSPI;"> 
</OBJECT> 
```

<span data-ttu-id="1d7f5-p102">OBJECT 标记用于定义程序中的 **RDS.DataControl** 组件。此标记包括以下两种类型的参数：</span><span class="sxs-lookup"><span data-stu-id="1d7f5-p102">The OBJECT tag defines the **RDS.DataControl** component in the program. The tag includes two types of parameters:</span></span>

  - <span data-ttu-id="1d7f5-111">与通用 OBJECT 标记关联的参数。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-111">Those associated with the generic OBJECT tag.</span></span>

  - <span data-ttu-id="1d7f5-112">特定于 **RDS.DataControl** 对象的参数。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-112">Those specific to the **RDS.DataControl** object.</span></span>

## <a name="generic-object-tag-parameters"></a><span data-ttu-id="1d7f5-113">通用 OBJECT 标记参数</span><span class="sxs-lookup"><span data-stu-id="1d7f5-113">Generic OBJECT Tag Parameters</span></span>

<span data-ttu-id="1d7f5-114">下表列出了与 OBJECT 标记关联的参数。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-114">The following table describes the parameters associated with the OBJECT tag.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1d7f5-115">参数</span><span class="sxs-lookup"><span data-stu-id="1d7f5-115">Parameter</span></span></p></th>
<th><p><span data-ttu-id="1d7f5-116">说明</span><span class="sxs-lookup"><span data-stu-id="1d7f5-116">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7f5-117"><strong><em>CLASSID</em></strong></span><span class="sxs-lookup"><span data-stu-id="1d7f5-117"><strong><em>CLASSID</em></strong></span></span></p></td>
<td><p><span data-ttu-id="1d7f5-p103">唯一，128 位数字，用于标识嵌入系统的对象类型。此标识符保存在本地计算机的系统注册表中。（有关 <strong>RDS.DataControl</strong> 对象的类 ID 的信息，请参阅 <a href="datacontrol-object-rds.md">RDS.DataControl 对象</a>。）</span><span class="sxs-lookup"><span data-stu-id="1d7f5-p103">A unique, 128-bit number that identifies the type of embedded object to the system. This identifier is maintained in the local computer's system registry. (For the class IDs of the <strong>RDS.DataControl</strong> object, see <a href="datacontrol-object-rds.md">RDS.DataControl Object</a>.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7f5-121"><strong><em>ID</em></strong></span><span class="sxs-lookup"><span data-stu-id="1d7f5-121"><strong><em>ID</em></strong></span></span></p></td>
<td><p><span data-ttu-id="1d7f5-122">为嵌入对象定义文档范围内的标识符，以便在代码中标识该对象。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-122">Defines a document-wide identifier for the embedded object that is used to identify it in code.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="rdsdatacontrol-tag-parameters"></a><span data-ttu-id="1d7f5-123">RDS.DataControl 标记参数</span><span class="sxs-lookup"><span data-stu-id="1d7f5-123">RDS.DataControl Tag Parameters</span></span>

<span data-ttu-id="1d7f5-p104">下表介绍特定于 **RDS.DataControl** 对象的参数。（有关 **RDS.DataControl** 对象参数的完整列表以及使用这些参数的场合，请参阅 [RDS.DataControl 对象](datacontrol-object-rds.md)。）</span><span class="sxs-lookup"><span data-stu-id="1d7f5-p104">The following table describes the parameters specific to the **RDS.DataControl** object. (For a complete list of the **RDS.DataControl** object parameters, and when to implement them, see [RDS.DataControl object](datacontrol-object-rds.md).)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1d7f5-126">参数</span><span class="sxs-lookup"><span data-stu-id="1d7f5-126">Parameter</span></span></p></th>
<th><p><span data-ttu-id="1d7f5-127">说明</span><span class="sxs-lookup"><span data-stu-id="1d7f5-127">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7f5-128"><a href="server-property-rds.md">服务器</a></span><span class="sxs-lookup"><span data-stu-id="1d7f5-128"><a href="server-property-rds.md">SERVER</a></span></span></p></td>
<td><p><span data-ttu-id="1d7f5-129">如果您使用的 HTTP，则值为前面 https:// 服务器计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-129">If you are using HTTP, the value is the name of the server computer preceded by https:// .</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7f5-130"><a href="connect-property-rds.md">连接</a></span><span class="sxs-lookup"><span data-stu-id="1d7f5-130"><a href="connect-property-rds.md">CONNECT</a></span></span></p></td>
<td><p><span data-ttu-id="1d7f5-131">提供 <strong>RDS.DataControl</strong> 连接到 SQL Server 的必要连接信息。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-131">Provides the necessary connection information for the <strong>RDS.DataControl</strong> to connect to SQL Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7f5-132"><a href="https://msdn.microsoft.com/library/jj248989(v=office.15)">SQL</a></span><span class="sxs-lookup"><span data-stu-id="1d7f5-132"><a href="https://msdn.microsoft.com/library/jj248989(v=office.15)">SQL</a></span></span></p></td>
<td><p><span data-ttu-id="1d7f5-133">设置或返回用于检索 <a href="recordset-object-ado.md">Recordset</a> 的查询字符串。</span><span class="sxs-lookup"><span data-stu-id="1d7f5-133">Sets or returns the query string used to retrieve the <a href="recordset-object-ado.md">Recordset</a>.</span></span></p></td>
</tr>
</tbody>
</table>

