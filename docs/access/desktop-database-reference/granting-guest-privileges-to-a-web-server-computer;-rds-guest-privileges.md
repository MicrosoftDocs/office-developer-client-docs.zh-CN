---
title: 向 web 服务器计算机授予来宾权限;RDS 来宾权限
TOCTitle: Granting guest privileges to a web server computer; RDS guest privileges
ms:assetid: 4ec9c05b-36f6-de22-b848-0cb8573f9dd1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249254(v=office.15)
ms:contentKeyID: 48544766
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8c0ee29125bf06ef51d1ac511838bdd09231e1a6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292123"
---
# <a name="granting-guest-privileges-to-a-web-server-computer-rds-guest-privileges"></a><span data-ttu-id="aa6ee-102">向 web 服务器计算机授予来宾权限;RDS 来宾权限</span><span class="sxs-lookup"><span data-stu-id="aa6ee-102">Granting guest privileges to a web server computer; RDS guest privileges</span></span>

<span data-ttu-id="aa6ee-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="aa6ee-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="aa6ee-104">必须将匿名 web 服务器帐户 (\_IUSR*ComputerName*) 添加到 web 服务器计算机上的来宾本地组中, 才能使用 RDS。</span><span class="sxs-lookup"><span data-stu-id="aa6ee-104">The anonymous web server account (IUSR\_*ComputerName*) must be added to the Guests local group on the web server computer to use RDS.</span></span>

<span data-ttu-id="aa6ee-105">**向 web 服务器计算机授予来宾权限**</span><span class="sxs-lookup"><span data-stu-id="aa6ee-105">**To grant guest privileges to a web server computer**</span></span>

1.  <span data-ttu-id="aa6ee-106">在 Microsoft Windows 2000 服务器计算机上, 单击 "**开始**", 指向 "**程序**", 指向 "**管理工具**", 然后单击 "**计算机管理**"。</span><span class="sxs-lookup"><span data-stu-id="aa6ee-106">On your Microsoft Windows 2000 Server computer, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>

2.  <span data-ttu-id="aa6ee-107">In the console tree, in **Local Users and Groups**, click **Groups**.</span><span class="sxs-lookup"><span data-stu-id="aa6ee-107">In the console tree, in **Local Users and Groups**, click **Groups**.</span></span>

3.  <span data-ttu-id="aa6ee-p101">Select the **Guests** local group. From the **Action** menu, choose **Properties**.</span><span class="sxs-lookup"><span data-stu-id="aa6ee-p101">Select the **Guests** local group. From the **Action** menu, choose **Properties**.</span></span>

4.  <span data-ttu-id="aa6ee-110">In the **Guests Properties** dialog box, click **Add**.</span><span class="sxs-lookup"><span data-stu-id="aa6ee-110">In the **Guests Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="aa6ee-111">如果 "**选择用户或组**" 对话框中的列表中未显示 "匿名 web 服务器" 帐户, 请在底部空白框\_中键入其名称 (IUSR*ComputerName*), 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="aa6ee-111">If the anonymous web server account does not appear in the list in the **Select Users or Groups** dialog box, type its name (IUSR\_*ComputerName*) into the bottom blank box, and then click **Add**.</span></span>

6.  <span data-ttu-id="aa6ee-112">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aa6ee-112">Click **OK**.</span></span>

