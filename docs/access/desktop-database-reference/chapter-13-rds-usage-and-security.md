---
title: 第 13 章：RDS 使用情况和安全
TOCTitle: 'Chapter 13: RDS Usage and Security'
ms:assetid: 78add8bb-f01a-2efb-33f0-430deebefe8f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249495(v=office.15)
ms:contentKeyID: 48545756
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4250235d433572944d311611c909c060d2e69da9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876104"
---
# <a name="chapter-13-rds-usage-and-security"></a><span data-ttu-id="06458-102">第 13 章：RDS 使用情况和安全</span><span class="sxs-lookup"><span data-stu-id="06458-102">Chapter 13: RDS Usage and Security</span></span>


<span data-ttu-id="06458-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="06458-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="06458-p101">本章中的信息可用于快速设置服务器和使用 RDS。本章包括在实现 RDS 时可能需要采取的特定配置步骤，描述了 RDS 与其他技术之间一些主要的关系，并帮助您解决在设置 RDS 解决方案时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="06458-p101">Use the information in this chapter to set up your server and use RDS quickly. This chapter includes specific configuration steps that you might need to take when implementing RDS, describes some of the key relationships between RDS and other technologies, and helps identify solutions to problems that you might encounter when setting up an RDS solution.</span></span>

<span data-ttu-id="06458-106">本部分包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="06458-106">This section contains information about:</span></span>

- [<span data-ttu-id="06458-107">配置 RDS</span><span class="sxs-lookup"><span data-stu-id="06458-107">Configuring RDS</span></span>](configuring-rds.md)

- <span data-ttu-id="06458-108">[授予 Web 服务器计算机; 来宾权限RDS 来宾权限\[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span><span class="sxs-lookup"><span data-stu-id="06458-108">[Granting Guest Privileges to a Web Server Computer; RDS guest privileges \[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span></span>

- [<span data-ttu-id="06458-109">将业务对象标记为"可安全编写脚本"</span><span class="sxs-lookup"><span data-stu-id="06458-109">Marking Business Objects as Safe for Scripting</span></span>](marking-business-objects-as-safe-for-scripting.md)

- [<span data-ttu-id="06458-110">在客户端上注册业务对象以用于 DCOM</span><span class="sxs-lookup"><span data-stu-id="06458-110">Registering Business Objects on the Client for Use with DCOM</span></span>](registering-business-objects-on-the-client-for-use-with-dcom.md)

- [<span data-ttu-id="06458-111">设置 DCOM 流封送处理格式</span><span class="sxs-lookup"><span data-stu-id="06458-111">Setting DCOM Stream Marshaling Format</span></span>](setting-dcom-stream-marshaling-format.md)

- [<span data-ttu-id="06458-112">启用 DLL 以在 DCOM 上运行</span><span class="sxs-lookup"><span data-stu-id="06458-112">Enabling a DLL to Run on DCOM</span></span>](enabling-a-dll-to-run-on-dcom.md)

- [<span data-ttu-id="06458-113">在 IIS 上配置虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="06458-113">Configuring Virtual Servers on IIS</span></span>](configuring-virtual-servers-on-iis.md)

- [<span data-ttu-id="06458-114">在 IIS 上指定每个处理器的线程数</span><span class="sxs-lookup"><span data-stu-id="06458-114">Specifying Threads Per Processor on IIS</span></span>](specifying-threads-per-processor-on-iis.md)

- [<span data-ttu-id="06458-115">保护 RDS 应用程序</span><span class="sxs-lookup"><span data-stu-id="06458-115">Securing RDS Applications</span></span>](securing-rds-applications.md)

- [<span data-ttu-id="06458-116">配置安全模式或无限制模式的 DataFactory</span><span class="sxs-lookup"><span data-stu-id="06458-116">Configuring DataFactory for Safe or Unrestricted Modes</span></span>](configuring-datafactory-for-safe-or-unrestricted-modes.md)

- [<span data-ttu-id="06458-117">Using Related Technologies with RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="06458-117">Using Related Technologies with RDS (ADO)</span></span>](using-related-technologies-with-rds.md)

- [<span data-ttu-id="06458-118">DataFactory Customization (ADO)</span><span class="sxs-lookup"><span data-stu-id="06458-118">DataFactory Customization (ADO)</span></span>](datafactory-customization.md)

- [<span data-ttu-id="06458-119">Troubleshooting RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="06458-119">Troubleshooting RDS (ADO)</span></span>](troubleshooting-rds.md)

