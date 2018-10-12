---
title: 避免在托管 Outlook 加载项中使用不受支持的技术
TOCTitle: Avoiding unsupported technologies in managed Outlook add-ins
ms:assetid: 365fd319-725f-4c4b-b6e7-575f78ed8bda
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb610014(v=office.15)
ms:contentKeyID: 55119789
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 3ad968b856e67183172adfd5829cdc06e7551ab5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405698"
---
# <a name="avoiding-unsupported-technologies-in-managed-outlook-add-ins"></a>避免在托管 Outlook 加载项中使用不受支持的技术

托管代码编程不支持先于 .NET Framework 出现的某些技术。 这些技术包括，协作数据对象 (CDO)、消息处理应用程序编程接口（MAPI，通常称为“扩展 MAPI”）和简单 MAPI。 这些技术是使用非托管代码进行设计和开发，Microsoft 不提供官方托管包装器来支持在托管应用程序中使用它们。 

有关详细信息，请参阅 [KB 266353：客户端消息处理开发的支持指南](https://go.microsoft.com/fwlink/?linkid=89209)一文中的“托管代码支持的 API”部分。

尽管如此，Microsoft Outlook 提供了许多对象模型功能，解决了以前只有 CDO 和 Exchange 客户端扩展 (ECE) 才能为开发人员解决的问题。 如果您在现有的非托管 Outlook 应用程序中使用 CDO，并且由于托管解决方案中缺少对 CDO 的支持导致您无法将应用程序迁移到托管代码中，您现在可以考虑只使用 Outlook 对象模型和主互操作程序集 (PIA) 将解决方案更新到托管代码中，而不必求助于 CDO。 

有关 Outlook 2007 为了减少对 CDO 和 ECE 的依赖而引入的更综合的 Outlook 平台的详细信息，请参阅 [What's New for Developers in Outlook 2007 (Part 1 of 2)](https://msdn.microsoft.com/library/bb226711\(v=office.15\))。

