---
title: 使用 ADO 可以执行的操作
TOCTitle: What You Can Do With ADO
ms:assetid: 98246cb0-aec6-6a77-c953-85895ad83a5d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249681(v=office.15)
ms:contentKeyID: 48546483
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: be66e8cf4179965f761db5873f4a2ac5de20c49d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874494"
---
# <a name="what-you-can-do-with-ado"></a>使用 ADO 可以执行的操作


**适用于**： Access 2013、 Office 2013

ADO 旨在向开发人员提供一个功能强大的逻辑对象模型，使用该模型，可以通过 OLE DB 系统接口以编程方式访问、编辑和更新广泛的数据源。ADO 最常见的用法是：在关系数据库中查询表，在应用程序中检索记录并显示结果，有可能允许用户更改数据并保存所做的更改。使用 ADO，还能够以编程方式执行下列操作：

  - 使用 SQL 查询数据库并显示结果。

  - 通过 Internet 访问文件存储区中的信息。

  - 操作电子邮件系统中的邮件和文件夹。

  - 将数据库中的数据保存到 XML 文件中。

  - 允许用户检索数据库表中的数据并对这些数据进行更改。

  - 创建和重新使用参数化数据库命令。

  - 执行存储过程。

  - 以动态方式创建一个名为 **Recordset** 的灵活结构，用来存放、导航和操作数据。

  - 执行事务数据库操作。

  - 基于运行时条件对数据库信息的本地副本进行筛选和排序。

  - 创建和操作数据库中的分层结果。

  - 将数据库中的字段绑定到能够识别数据的组件。

  - 创建已断开连接的远程 **Recordset** 。

ADO 必须公开广泛的选项和设置，才能提供这样的灵活性。因此，一定要采取系统的方法来了解如何在应用程序中使用 ADO，并将每个目标都分成可管理的部分。

大多数 ADO 程序都涉及四个主要操作：获取数据、检查数据、编辑数据和更新数据。接下来的四章将更详细地介绍各个操作。

在继续之前，请先熟悉 ADO 对象模型中的对象。然后查看 [HelloData：简单 ADO 应用程序](hellodata-a-simple-ado-application.md)，这个应用程序是用 Visual Basic 编写的，可用来执行这四个主要的 ADO 操作。

