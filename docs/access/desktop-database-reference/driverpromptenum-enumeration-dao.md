---
title: DriverPromptEnum Enumeration (DAO)
TOCTitle: DriverPromptEnum Enumeration
ms:assetid: 8dda5e9f-a58f-a62d-eb49-5966d4a1e086
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197361(v=office.15)
ms:contentKeyID: 48546266
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c20542c89537f16f20c9d3e30cbc14ce115bf4d6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468914"
---
# <a name="driverpromptenum-enumeration-dao"></a><span data-ttu-id="1e6af-102">DriverPromptEnum Enumeration (DAO)</span><span class="sxs-lookup"><span data-stu-id="1e6af-102">DriverPromptEnum Enumeration (DAO)</span></span>


<span data-ttu-id="1e6af-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1e6af-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1e6af-104">指定是否以及何时提示用户建立连接。</span><span class="sxs-lookup"><span data-stu-id="1e6af-104">Specifies if and when to prompt the user to establish a connection.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1e6af-105">名称</span><span class="sxs-lookup"><span data-stu-id="1e6af-105">Name</span></span></p></th>
<th><p><span data-ttu-id="1e6af-106">值</span><span class="sxs-lookup"><span data-stu-id="1e6af-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1e6af-107">说明</span><span class="sxs-lookup"><span data-stu-id="1e6af-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e6af-108">dbDriverComplete</span><span class="sxs-lookup"><span data-stu-id="1e6af-108">dbDriverComplete</span></span></p></td>
<td><p><span data-ttu-id="1e6af-109">0</span><span class="sxs-lookup"><span data-stu-id="1e6af-109">0</span></span></p></td>
<td><p><span data-ttu-id="1e6af-110">如果所提供的连接字符串包括 DSN 关键字，驱动程序管理器将使用所提供的字符串建立连接，否则，它将按照指定了 <strong>dbDriverPrompt</strong> 时的方式工作。</span><span class="sxs-lookup"><span data-stu-id="1e6af-110">If the connection string provided includes the DSN keyword, the driver manager uses the string as provided in connect, otherwise it behaves as it does when <strong>dbDriverPrompt</strong> is specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6af-111">dbDriverCompleteRequired</span><span class="sxs-lookup"><span data-stu-id="1e6af-111">dbDriverCompleteRequired</span></span></p></td>
<td><p><span data-ttu-id="1e6af-112">3</span><span class="sxs-lookup"><span data-stu-id="1e6af-112">3</span></span></p></td>
<td><p><span data-ttu-id="1e6af-113">（默认值）其行为类似于 <strong>dbDriverComplete</strong>，不同之处在于，驱动程序将禁用完成连接所不需要的任何信息对应的控件。</span><span class="sxs-lookup"><span data-stu-id="1e6af-113">(Default) Behaves like <strong>dbDriverComplete</strong> except the driver disables the controls for any information not required to complete the connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e6af-114">dbDriverNoPrompt</span><span class="sxs-lookup"><span data-stu-id="1e6af-114">dbDriverNoPrompt</span></span></p></td>
<td><p><span data-ttu-id="1e6af-115">1</span><span class="sxs-lookup"><span data-stu-id="1e6af-115">1</span></span></p></td>
<td><p><span data-ttu-id="1e6af-p101">驱动程序管理器使用所提供的连接字符串建立连接。如果提供的信息不足，则返回一个可捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="1e6af-p101">The driver manager uses the connection string provided in connect. If sufficient information is not provided, a trappable error is returned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e6af-118">dbDriverPrompt</span><span class="sxs-lookup"><span data-stu-id="1e6af-118">dbDriverPrompt</span></span></p></td>
<td><p><span data-ttu-id="1e6af-119">2</span><span class="sxs-lookup"><span data-stu-id="1e6af-119">2</span></span></p></td>
<td><p><span data-ttu-id="1e6af-p102">驱动程序管理器显示<strong>“ODBC 数据源”</strong>对话框。用来建立连接的连接字符串是由用户通过对话框选择和填写的数据源名称 (DSN) 构造的。</span><span class="sxs-lookup"><span data-stu-id="1e6af-p102">The driver manager displays the <strong>ODBC Data Sources</strong> dialog box. The connection string used to establish the connection is constructed from the data source name (DSN) selected and completed by the user via the dialog boxes.</span></span></p></td>
</tr>
</tbody>
</table>
