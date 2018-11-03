---
title: 尽量减少日志文件空间使用率
TOCTitle: Minimizing log file space usage
ms:assetid: d527c313-35ad-c30e-6ea1-ddfeff1fe890
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250073(v=office.15)
ms:contentKeyID: 48547960
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2c462641616c126c7732433fc8b7d23bb137b06a
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944765"
---
# <a name="minimizing-log-file-space-usage"></a><span data-ttu-id="dbc24-102">尽量减少日志文件空间使用率</span><span class="sxs-lookup"><span data-stu-id="dbc24-102">Minimizing log file space usage</span></span>

<span data-ttu-id="dbc24-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dbc24-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dbc24-p101">如果 SQL Server 数据库上存在大量的活动，那么日志文件可能很快就会写满（从而阻碍服务器的运行）。您可以将日志文件设置为 **在检查点截断日志** ，以显著延长数据库日志文件的使用时间。</span><span class="sxs-lookup"><span data-stu-id="dbc24-p101">A log file may fill quickly (thus halting the server) if there is a large volume of activity on an SQL Server database. You can set the log file to **Truncate on Checkpoint** to significantly extend the life of the log file for a database.</span></span>

<span data-ttu-id="dbc24-106">**在 Microsoft SQL Server 6.5 中启用"在检查点截断日志"功能的方法**</span><span class="sxs-lookup"><span data-stu-id="dbc24-106">**To enable Truncate on Checkpoint in Microsoft SQL Server 6.5**</span></span>

1.  <span data-ttu-id="dbc24-107">启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库设备"树。</span><span class="sxs-lookup"><span data-stu-id="dbc24-107">Start Microsoft SQL Server Enterprise Manager, open the tree for the Server, and then open the Database Devices tree.</span></span>

2.  <span data-ttu-id="dbc24-108">双击要启用此功能的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="dbc24-108">Double-click the name of the database on which this feature will be enabled.</span></span>

3.  <span data-ttu-id="dbc24-109">从**数据库**选项卡中，选择**截断**。</span><span class="sxs-lookup"><span data-stu-id="dbc24-109">From the **Database** tab, select **Truncate**.</span></span>

4.  <span data-ttu-id="dbc24-110">从**选项**选项卡中，选择**在检查点截断日志**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dbc24-110">From the **Options** tab, select **Truncate Log on Checkpoint**, and then click **OK**.</span></span>

<span data-ttu-id="dbc24-111">**在 Microsoft SQL Server 7.0 中启用"在检查点截断日志"功能的方法**</span><span class="sxs-lookup"><span data-stu-id="dbc24-111">**To enable Truncate on Checkpoint in Microsoft SQL Server 7.0**</span></span>

1.  <span data-ttu-id="dbc24-112">启动 Microsoft SQL Server 企业管理器，打开"服务器"树，然后打开"数据库"树。</span><span class="sxs-lookup"><span data-stu-id="dbc24-112">Start Microsoft SQL Server Enterprise Manager, open the tree for the Server, and then open the Databases tree.</span></span>

2.  <span data-ttu-id="dbc24-113">右键单击此功能将启用在其，选择**属性**的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="dbc24-113">Right-click the name of the database on which this feature will be enabled and choose **Properties**.</span></span>

3.  <span data-ttu-id="dbc24-114">从**选项**选项卡中，选择**在检查点截断日志**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dbc24-114">From the **Options** tab, select **Truncate Log on Checkpoint**, and then click **OK**.</span></span>

<span data-ttu-id="dbc24-115">有关 **在检查点截断日志** 功能的详细信息，请参阅 Microsoft SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="dbc24-115">For more information about the **Truncate on Checkpoint** feature, see the Microsoft SQL Server documentation.</span></span>

