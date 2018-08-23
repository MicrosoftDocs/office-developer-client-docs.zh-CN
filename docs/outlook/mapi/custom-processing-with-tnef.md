---
title: 自定义处理与 TNEF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c015335a-8fcd-4b03-abb9-9b6b72000e13
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d9bbba40e5159221cfb3b3692b597b07fb606936
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584665"
---
# <a name="custom-processing-with-tnef"></a><span data-ttu-id="918b5-103">自定义处理与 TNEF</span><span class="sxs-lookup"><span data-stu-id="918b5-103">Custom processing with TNEF</span></span>

<span data-ttu-id="918b5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="918b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="918b5-105">传输提供程序可以使用自定义处理处理附件本身上的属性、 单独传输附件或传输这些邮件系统的附件模型通过。</span><span class="sxs-lookup"><span data-stu-id="918b5-105">Transport providers can use custom processing to process the properties on an attachment itself, transmit attachments separately, or transmit them through the messaging system's attachment model.</span></span> <span data-ttu-id="918b5-106">TNEF 使用允许传输提供程序以发送除了邮件附件并将其重新连接接收端的机制。</span><span class="sxs-lookup"><span data-stu-id="918b5-106">TNEF uses a mechanism that enables the transport provider to send the attachments apart from the message and reconnect them on the receiving side.</span></span>
  

