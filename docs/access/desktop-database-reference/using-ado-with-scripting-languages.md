---
title: 在脚本语言中使用 ADO
TOCTitle: Using ADO with Scripting Languages
ms:assetid: 2e163ffb-22fe-36f5-9960-8f6bcb148183
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249074(v=office.15)
ms:contentKeyID: 48543985
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ffab726a38b5cd6890bff694c52156d3f45a40be
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870378"
---
# <a name="using-ado-with-scripting-languages"></a><span data-ttu-id="ff618-102">将 ADO 与脚本语言结合使用</span><span class="sxs-lookup"><span data-stu-id="ff618-102">Using ADO with Scripting Languages</span></span>


<span data-ttu-id="ff618-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff618-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ff618-104">在脚本环境中，您可以采用 ADO 通过服务器端脚本公开数据。</span><span class="sxs-lookup"><span data-stu-id="ff618-104">Within a scripting environment, ADO allows you to expose data by way of server-side scripting.</span></span> <span data-ttu-id="ff618-105">在此方案中，使用 ADO 作为基础 OLE DB 提供程序，ADO 和引用给定数据存储所需的其他所有组件都安装在运行 Internet 信息服务 (IIS) 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="ff618-105">In this scenario, ADO, the underlying OLE DB provider that it utilizes, and any other components needed to reference a given data store are installed on a server running Internet Information Services (IIS).</span></span> <span data-ttu-id="ff618-106">例如，通过使用 Active Server Pages (ASP)，ADO 是可以生成 HTML 的脚本中引用的组件。</span><span class="sxs-lookup"><span data-stu-id="ff618-106">Using Active Server Pages (ASP), ADO is a component referenced in a script that can generate HTML, for example.</span></span> <span data-ttu-id="ff618-107">此 HTML 内容可以通过 HTTP 传递给客户端 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="ff618-107">This HTML content can be passed via HTTP to a client web browser.</span></span> <span data-ttu-id="ff618-108">通过使用脚本，网页可以发送回服务器端脚本，从而使您可以更新、 遍历或查看特定的数据的操作。</span><span class="sxs-lookup"><span data-stu-id="ff618-108">Through the use of scripting, the webpage can send actions back to the server-side script, allowing you to update, traverse, or view specific data.</span></span>

## <a name="odbc-data-sources"></a><span data-ttu-id="ff618-109">ODBC 数据源</span><span class="sxs-lookup"><span data-stu-id="ff618-109">ODBC Data Sources</span></span>

<span data-ttu-id="ff618-p102">脚本与非脚本 ADO 代码之间一个显著的区别是 ODBC 数据源（如果使用）。对于非脚本的应用程序，可以在 ODBC 数据源管理器中创建一个用户 DSN。对于运行在 IIS 下的脚本，则必须创建一个系统 DSN，否则脚本将无法识别您创建的数据源。此规则适用于通过 Microsoft IIS 使用 Microsoft OLE DB Provider for ODBC 的任何 ADO 脚本应用程序。</span><span class="sxs-lookup"><span data-stu-id="ff618-p102">One notable difference between scripting and non-scripting ADO code is the ODBC Data Source, if used. For non-scripting applications, you can create a User DSN in the ODBC Data Source Administrator. For scripts that are running under IIS, you must create a System DSN; otherwise your scripts won't recognize the data source you created. This applies to any ADO scripting application using the Microsoft OLE DB Provider for ODBC through Microsoft IIS.</span></span>

## <a name="referencing-the-ado-library"></a><span data-ttu-id="ff618-114">引用 ADO 库</span><span class="sxs-lookup"><span data-stu-id="ff618-114">Referencing the ADO Library</span></span>

<span data-ttu-id="ff618-115">脚本语言中不可用。</span><span class="sxs-lookup"><span data-stu-id="ff618-115">N/A with scripting languages.</span></span>

## <a name="handling-events"></a><span data-ttu-id="ff618-116">处理事件</span><span class="sxs-lookup"><span data-stu-id="ff618-116">Handling events</span></span>

<span data-ttu-id="ff618-117">脚本语言中不可用。</span><span class="sxs-lookup"><span data-stu-id="ff618-117">N/A with scripting languages.</span></span>

<span data-ttu-id="ff618-118">以下主题中包含有关在脚本语言中使用 ADO 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="ff618-118">The following topics contain more specific information about using ADO with scripting languages:</span></span>

- [<span data-ttu-id="ff618-119">JScript ADO 编程</span><span class="sxs-lookup"><span data-stu-id="ff618-119">JScript ADO Programming</span></span>](jscript-ado-programming.md)

- [<span data-ttu-id="ff618-120">VBScript ADO 编程</span><span class="sxs-lookup"><span data-stu-id="ff618-120">VBScript ADO Programming</span></span>](vbscript-ado-programming.md)