---
title: 第 13 章： RDS 用法和安全性
TOCTitle: 'Chapter 13: RDS usage and security'
ms:assetid: 78add8bb-f01a-2efb-33f0-430deebefe8f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249495(v=office.15)
ms:contentKeyID: 48545756
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 21f1484850a91d1fbdbe687f171e8ae9dfe4a5cd
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936467"
---
# <a name="chapter-13-rds-usage-and-security"></a><span data-ttu-id="b72df-102">第 13 章： RDS 用法和安全性</span><span class="sxs-lookup"><span data-stu-id="b72df-102">Chapter 13: RDS usage and security</span></span>

<span data-ttu-id="b72df-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b72df-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b72df-p101">本章中的信息可用于快速设置服务器和使用 RDS。本章包括在实现 RDS 时可能需要采取的特定配置步骤，描述了 RDS 与其他技术之间一些主要的关系，并帮助您解决在设置 RDS 解决方案时可能遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="b72df-p101">Use the information in this chapter to set up your server and use RDS quickly. This chapter includes specific configuration steps that you might need to take when implementing RDS, describes some of the key relationships between RDS and other technologies, and helps identify solutions to problems that you might encounter when setting up an RDS solution.</span></span>

<span data-ttu-id="b72df-106">本部分包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="b72df-106">This section contains information about:</span></span>

- [<span data-ttu-id="b72df-107">配置安全或无限制模式的 DataFactory</span><span class="sxs-lookup"><span data-stu-id="b72df-107">Configuring DataFactory for safe or unrestricted modes</span></span>](configuring-datafactory-for-safe-or-unrestricted-modes.md)
- [<span data-ttu-id="b72df-108">配置 RDS</span><span class="sxs-lookup"><span data-stu-id="b72df-108">Configuring RDS</span></span>](configuring-rds.md)
- [<span data-ttu-id="b72df-109">在 IIS 上配置虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="b72df-109">Configuring virtual servers on IIS</span></span>](configuring-virtual-servers-on-iis.md)
- [<span data-ttu-id="b72df-110">DataFactory 自定义 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b72df-110">DataFactory customization (ADO)</span></span>](datafactory-customization.md)
- [<span data-ttu-id="b72df-111">启用 DLL 以在 DCOM 上运行</span><span class="sxs-lookup"><span data-stu-id="b72df-111">Enabling a DLL to run on DCOM</span></span>](enabling-a-dll-to-run-on-dcom.md)
- <span data-ttu-id="b72df-112">[授予 web 服务器计算机; 来宾权限RDS 来宾权限\[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span><span class="sxs-lookup"><span data-stu-id="b72df-112">[Granting guest privileges to a web server computer; RDS guest privileges \[ADO\]](granting-guest-privileges-to-a-web-server-computer;-rds-guest-privileges.md)</span></span>
- [<span data-ttu-id="b72df-113">标记为可安全编写脚本的业务对象</span><span class="sxs-lookup"><span data-stu-id="b72df-113">Marking business objects as safe for scripting</span></span>](marking-business-objects-as-safe-for-scripting.md)
- [<span data-ttu-id="b72df-114">注册业务对象的客户端上使用 DCOM</span><span class="sxs-lookup"><span data-stu-id="b72df-114">Registering business objects on the client for use with DCOM</span></span>](registering-business-objects-on-the-client-for-use-with-dcom.md)
- [<span data-ttu-id="b72df-115">保护 RDS 应用程序</span><span class="sxs-lookup"><span data-stu-id="b72df-115">Securing RDS applications</span></span>](securing-rds-applications.md)
- [<span data-ttu-id="b72df-116">设置 DCOM 流封送处理格式</span><span class="sxs-lookup"><span data-stu-id="b72df-116">Setting DCOM stream marshaling format</span></span>](setting-dcom-stream-marshaling-format.md)
- [<span data-ttu-id="b72df-117">在 IIS 上指定每个处理器的线程数</span><span class="sxs-lookup"><span data-stu-id="b72df-117">Specifying threads per processor on IIS</span></span>](specifying-threads-per-processor-on-iis.md)
- [<span data-ttu-id="b72df-118">Troubleshooting RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="b72df-118">Troubleshooting RDS (ADO)</span></span>](troubleshooting-rds.md)
- [<span data-ttu-id="b72df-119">使用相关的技术与 RDS (ADO)</span><span class="sxs-lookup"><span data-stu-id="b72df-119">Using related technologies with RDS (ADO)</span></span>](using-related-technologies-with-rds.md)














