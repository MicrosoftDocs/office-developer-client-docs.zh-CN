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
# <a name="using-ado-with-scripting-languages"></a>将 ADO 与脚本语言结合使用


**适用于**： Access 2013、 Office 2013

在脚本环境中，您可以采用 ADO 通过服务器端脚本公开数据。 在此方案中，使用 ADO 作为基础 OLE DB 提供程序，ADO 和引用给定数据存储所需的其他所有组件都安装在运行 Internet 信息服务 (IIS) 的服务器上。 例如，通过使用 Active Server Pages (ASP)，ADO 是可以生成 HTML 的脚本中引用的组件。 此 HTML 内容可以通过 HTTP 传递给客户端 web 浏览器。 通过使用脚本，网页可以发送回服务器端脚本，从而使您可以更新、 遍历或查看特定的数据的操作。

## <a name="odbc-data-sources"></a>ODBC 数据源

脚本与非脚本 ADO 代码之间一个显著的区别是 ODBC 数据源（如果使用）。对于非脚本的应用程序，可以在 ODBC 数据源管理器中创建一个用户 DSN。对于运行在 IIS 下的脚本，则必须创建一个系统 DSN，否则脚本将无法识别您创建的数据源。此规则适用于通过 Microsoft IIS 使用 Microsoft OLE DB Provider for ODBC 的任何 ADO 脚本应用程序。

## <a name="referencing-the-ado-library"></a>引用 ADO 库

脚本语言中不可用。

## <a name="handling-events"></a>处理事件

脚本语言中不可用。

以下主题中包含有关在脚本语言中使用 ADO 的详细信息：

- [JScript ADO 编程](jscript-ado-programming.md)

- [VBScript ADO 编程](vbscript-ado-programming.md)