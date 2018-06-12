---
title: 传输中性封装格式 (TNEF)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 98d4fe3c-3908-4cd2-bfdb-ff1874a80b24
description: 上次修改时间： 2013 年 3 月 12 日
ms.openlocfilehash: 34b64df25cb2f7f591f7c799dec957a0072840dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779001"
---
# <a name="transport-neutral-encapsulation-format-tnef"></a><span data-ttu-id="ac684-103">传输中性封装格式 (TNEF)</span><span class="sxs-lookup"><span data-stu-id="ac684-103">Transport-Neutral Encapsulation Format (TNEF)</span></span>

 
  
<span data-ttu-id="ac684-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac684-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac684-105">TNEF 是用于转换的 MAPI 属性集的格式 — MAPI 邮件 — 到串行数据流。</span><span class="sxs-lookup"><span data-stu-id="ac684-105">TNEF is a format for converting a set of MAPI properties—a MAPI message—into a serial data stream.</span></span> <span data-ttu-id="ac684-106">由传输提供程序需要进行编码通过不直接支持这些属性的消息系统传输的 MAPI 邮件属性主要用于 TNEF 函数。</span><span class="sxs-lookup"><span data-stu-id="ac684-106">The TNEF functions are primarily used by transport providers that need to encode MAPI message properties for transmission through a messaging system that does not support those properties directly.</span></span> <span data-ttu-id="ac684-107">例如，基于 SMTP 传输使用 TNEF 编码属性类似**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))，其结构中的 SMTP 邮件没有直接的表示形式。</span><span class="sxs-lookup"><span data-stu-id="ac684-107">For example, an SMTP-based transport uses TNEF to encode properties like **PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)), which do not have direct representations in the structure of an SMTP message.</span></span>
  
<span data-ttu-id="ac684-108">TNEF 实现定义多个特定于 TNEF 的属性，其中每个对应于特定的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ac684-108">The TNEF implementation defines several TNEF-specific attributes, each of which corresponds to a particular MAPI property.</span></span> <span data-ttu-id="ac684-109">这些属性用于编码到 TNEF 流及其各自的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ac684-109">These attributes are used to encode their respective MAPI properties into the TNEF stream.</span></span> <span data-ttu-id="ac684-110">此外，定义特殊属性可用于封装不具有特定属性对应于其任何 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="ac684-110">In addition, a special attribute is defined that can be used to encapsulate any MAPI property that does not have a specific attribute corresponding to it.</span></span> <span data-ttu-id="ac684-111">这些属性定义的原因，而不是只需使用统一的编码的所有 MAPI 属性的方法 — 是启用向后兼容的非 MAPI 兼容的软件正在使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="ac684-111">The reason these attributes are defined — instead of simply using a uniform encoding method for all MAPI properties — is to enable backward compatibility with non-MAPI-compliant software that is using TNEF.</span></span>
  
<span data-ttu-id="ac684-112">本节的其余部分介绍的结构和 TNEF 流，MAPI 属性和 TNEF 属性和重要注意事项某些 TNEF 属性之间的映射的语法。</span><span class="sxs-lookup"><span data-stu-id="ac684-112">The remainder of this section describes the structure and syntax of a TNEF stream, the mapping between MAPI properties and TNEF attributes, and important considerations for certain TNEF attributes.</span></span>
  

