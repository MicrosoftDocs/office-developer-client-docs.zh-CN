---
title: 第 13 章：RDS 使用和安全性
TOCTitle: 'Chapter 13: RDS usage and security'
ms:assetid: 78add8bb-f01a-2efb-33f0-430deebefe8f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249495(v=office.15)
ms:contentKeyID: 48545756
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4c0753a53a2001a6c5c96ae2ceb801ee6eb75a5e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716017"
---
# <a name="chapter-13-rds-usage-and-security"></a><span data-ttu-id="f9f45-102">第 13 章：RDS 使用和安全性</span><span class="sxs-lookup"><span data-stu-id="f9f45-102">Chapter 13: RDS usage and security</span></span>

<span data-ttu-id="f9f45-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f9f45-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f9f45-p101">本章中的信息可用于快速设置服务器和使用 RDS。本章包括在实现 RDS 时可能需要采取的特定配置步骤，描述了 RDS 与其他技术之间一些主要的关系，并帮助您解决在设置 RDS 解决方案时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="f9f45-p101">Use the information in this chapter to set up your server and use RDS quickly. This chapter includes specific configuration steps that you might need to take when implementing RDS, describes some of the key relationships between RDS and other technologies, and helps identify solutions to problems that you might encounter when setting up an RDS solution.</span></span>

<span data-ttu-id="f9f45-106">本部分包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="f9f45-106">This section contains information about:</span></span>

- [<span data-ttu-id="f9f45-107">针对安全或无限制模式配置 DataFactory</span><span class="sxs-lookup"><span data-stu-id="f9f45-107">Configuring DataFactory for safe or unrestricted modes</span></span>](configuring-datafactory-for-safe-or-unrestricted-modes.md)
- [<span data-ttu-id="f9f45-108">配置 RDS</span><span class="sxs-lookup"><span data-stu-id="f9f45-108">Configuring RDS</span></span>](configuring-rds.md)
- [<span data-ttu-id="f9f45-109">在 IIS 上配置虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="f9f45-109">Configuring virtual servers on IIS</span></span>](configuring-virtual-servers-on-iis.md)
- [<span data-ttu-id="f9f45-110">DataFactory 自定义 (ADO)</span><span class="sxs-lookup"><span data-stu-id="f9f45-110">DataFactory customization (ADO)</span></span>](datafactory-customization.md)
- [<span data-ttu-id="f9f45-111">启用 DLL 以在 DCOM 上运行</span><span class="sxs-lookup"><span data-stu-id="f9f45-111">Enabling a DLL to run on DCOM</span></span>](enabling-a-dll-to-run-on-dcom.md)
- <span data-ttu-id="f9f45-112">[授予 web 服务器计算机; 来宾权限RDS 来宾权限\[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span><span class="sxs-lookup"><span data-stu-id="f9f45-112">[Granting guest privileges to a web server computer; RDS guest privileges \[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span></span>
- [<span data-ttu-id="f9f45-113">将业务对象标记为脚本安全</span><span class="sxs-lookup"><span data-stu-id="f9f45-113">Marking business objects as safe for scripting</span></span>](marking-business-objects-as-safe-for-scripting.md)
- [<span data-ttu-id="f9f45-114">在客户端上注册业务对象以与 DCOM 结合使用</span><span class="sxs-lookup"><span data-stu-id="f9f45-114">Registering business objects on the client for use with DCOM</span></span>](registering-business-objects-on-the-client-for-use-with-dcom.md)
- [<span data-ttu-id="f9f45-115">保护 RDS 应用程序安全</span><span class="sxs-lookup"><span data-stu-id="f9f45-115">Securing RDS applications</span></span>](securing-rds-applications.md)
- [<span data-ttu-id="f9f45-116">设置 DCOM 流封送格式</span><span class="sxs-lookup"><span data-stu-id="f9f45-116">Setting DCOM stream marshaling format</span></span>](setting-dcom-stream-marshaling-format.md)
- [<span data-ttu-id="f9f45-117">在 IIS 上指定每个处理器的线程数</span><span class="sxs-lookup"><span data-stu-id="f9f45-117">Specifying threads per processor on IIS</span></span>](specifying-threads-per-processor-on-iis.md)
- [<span data-ttu-id="f9f45-118">Troubleshooting RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="f9f45-118">Troubleshooting RDS (ADO)</span></span>](troubleshooting-rds.md)
- [<span data-ttu-id="f9f45-119">使用相关的技术与 RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="f9f45-119">Using related technologies with RDS (ADO)</span></span>](using-related-technologies-with-rds.md)














