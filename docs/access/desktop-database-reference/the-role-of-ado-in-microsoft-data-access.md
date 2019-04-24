---
title: ADO 在 Microsoft 数据访问中的角色
TOCTitle: The Role of ADO in Microsoft Data Access
ms:assetid: e9087ec8-850b-ebbe-369a-a5987a528de6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250180(v=office.15)
ms:contentKeyID: 48548433
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 91f591513e0a35a70d157b0a640c87efc961fe22
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314033"
---
# <a name="role-of-ado-in-microsoft-data-access"></a>ADO 在 Microsoft 数据访问中的角色

**适用于**：Access 2013、Office 2013

Microsoft 数据访问组件 (MDAC) 提供了独立于数据存储、工具和语言的数据访问功能。它为使用实际上任何可用的数据存储提供了高级别、易用的接口，以及低级别、高性能的接口。可以使用此灵活性来集成不同的数据存储，并使用您选择的工具、应用程序和平台服务针对您的需要创建正确的解决方案。这些技术为在 Microsoft Windows 操作系统中进行常规用途的数据访问提供了基本框架。

MDAC 中有三项主要技术。ActiveX 数据对象 (ADO) 是连接 OLE DB 的高级别、易用的接口。OLE DB 是连接多种数据存储的低级别、高性能的接口。ADO 和 OLE DB 都可以用来处理关系型（表格化）数据和非关系型（分层或流）数据。最后，开放式数据库连接 (ODBC) 是另一个低级别、高性能的接口，它是专门为关系数据存储设计的。

ADO 提供了客户端或中间层应用程序与低级别的 OLE DB 接口之间的抽象层。ADO 使用一组小型自动化对象来提供与 OLE DB 的简单有效的接口。使用更高级别语言（例如，Visual Basic，甚至 VBScript）的开发人员通常希望访问数据而不想了解 COM 和 OLE DB 的复杂技术，而此接口使 ADO 成为他们的完美选择。

