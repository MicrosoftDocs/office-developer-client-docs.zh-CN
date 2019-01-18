---
title: 授予 web 服务器计算机; 来宾权限RDS 来宾权限
TOCTitle: Granting guest privileges to a web server computer; RDS guest privileges
ms:assetid: 4ec9c05b-36f6-de22-b848-0cb8573f9dd1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249254(v=office.15)
ms:contentKeyID: 48544766
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8c0ee29125bf06ef51d1ac511838bdd09231e1a6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700547"
---
# <a name="granting-guest-privileges-to-a-web-server-computer-rds-guest-privileges"></a><span data-ttu-id="ea375-102">授予 web 服务器计算机; 来宾权限RDS 来宾权限</span><span class="sxs-lookup"><span data-stu-id="ea375-102">Granting guest privileges to a web server computer; RDS guest privileges</span></span>

<span data-ttu-id="ea375-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ea375-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ea375-104">匿名 web 服务器帐户 (IUSR\_*ComputerName*) 必须添加到 Guests 本地组的 web 服务器计算机上才能使用 rds。</span><span class="sxs-lookup"><span data-stu-id="ea375-104">The anonymous web server account (IUSR\_*ComputerName*) must be added to the Guests local group on the web server computer to use RDS.</span></span>

<span data-ttu-id="ea375-105">**授予 web 服务器计算机来宾权限**</span><span class="sxs-lookup"><span data-stu-id="ea375-105">**To grant guest privileges to a web server computer**</span></span>

1.  <span data-ttu-id="ea375-106">Microsoft Windows 2000 Server 计算机上单击**开始**，指向**程序**、**管理工具**，，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="ea375-106">On your Microsoft Windows 2000 Server computer, click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>

2.  <span data-ttu-id="ea375-107">在控制台树中，在**本地用户和组**中，单击**组**。</span><span class="sxs-lookup"><span data-stu-id="ea375-107">In the console tree, in **Local Users and Groups**, click **Groups**.</span></span>

3.  <span data-ttu-id="ea375-108">选择的**Guests**本地组。</span><span class="sxs-lookup"><span data-stu-id="ea375-108">Select the **Guests** local group.</span></span> <span data-ttu-id="ea375-109">从**操作**菜单中，选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ea375-109">From the **Action** menu, choose **Properties**.</span></span>

4.  <span data-ttu-id="ea375-110">在**Guests 属性**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ea375-110">In the **Guests Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="ea375-111">如果匿名 web 服务器帐户未显示在**选择用户或组**对话框中的列表，请键入其名称 (IUSR\_*ComputerName*) 到空白底部框中，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="ea375-111">If the anonymous web server account does not appear in the list in the **Select Users or Groups** dialog box, type its name (IUSR\_*ComputerName*) into the bottom blank box, and then click **Add**.</span></span>

6.  <span data-ttu-id="ea375-112">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ea375-112">Click **OK**.</span></span>

