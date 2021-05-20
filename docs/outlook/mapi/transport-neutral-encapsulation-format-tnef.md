---
title: 传输中性封装格式 (TNEF)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 98d4fe3c-3908-4cd2-bfdb-ff1874a80b24
description: 上次修改时间：2013 年 3 月 12 日
ms.openlocfilehash: d902039fa1081e30947ddd8f70ead9ae7acec06a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428688"
---
# <a name="transport-neutral-encapsulation-format-tnef"></a><span data-ttu-id="49202-103">传输中性封装格式 (TNEF)</span><span class="sxs-lookup"><span data-stu-id="49202-103">Transport-Neutral Encapsulation Format (TNEF)</span></span>

 
  
<span data-ttu-id="49202-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="49202-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="49202-105">TNEF 是用于将一组 MAPI 属性（MAPI 邮件）转换为串行数据流的一种格式。</span><span class="sxs-lookup"><span data-stu-id="49202-105">TNEF is a format for converting a set of MAPI properties—a MAPI message—into a serial data stream.</span></span> <span data-ttu-id="49202-106">TNEF 函数主要由需要编码 MAPI 邮件属性的传输提供程序使用，以通过不支持这些属性直接支持的邮件系统传输。</span><span class="sxs-lookup"><span data-stu-id="49202-106">The TNEF functions are primarily used by transport providers that need to encode MAPI message properties for transmission through a messaging system that does not support those properties directly.</span></span> <span data-ttu-id="49202-107">例如，基于 SMTP 的传输使用 TNEF 对 **PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)) 等属性进行编码，这些属性在 SMTP 邮件的结构中没有直接表示形式。</span><span class="sxs-lookup"><span data-stu-id="49202-107">For example, an SMTP-based transport uses TNEF to encode properties like **PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md)), which do not have direct representations in the structure of an SMTP message.</span></span>
  
<span data-ttu-id="49202-108">TNEF 实现定义几个特定于 TNEF 的属性，每个属性对应于一个特定的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="49202-108">The TNEF implementation defines several TNEF-specific attributes, each of which corresponds to a particular MAPI property.</span></span> <span data-ttu-id="49202-109">这些属性用于将各自的 MAPI 属性编码到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="49202-109">These attributes are used to encode their respective MAPI properties into the TNEF stream.</span></span> <span data-ttu-id="49202-110">此外，还定义了一个特殊属性，可用于封装任何没有与之对应的特定属性的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="49202-110">In addition, a special attribute is defined that can be used to encapsulate any MAPI property that does not have a specific attribute corresponding to it.</span></span> <span data-ttu-id="49202-111">定义这些属性（而不只是针对所有 MAPI 属性使用统一编码方法）的原因是启用与非 MAPI 兼容软件（使用 TNEF）的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="49202-111">The reason these attributes are defined — instead of simply using a uniform encoding method for all MAPI properties — is to enable backward compatibility with non-MAPI-compliant software that is using TNEF.</span></span>
  
<span data-ttu-id="49202-112">本节的其余部分介绍了 TNEF 流的结构和语法、MAPI 属性和 TNEF 属性之间的映射，以及某些 TNEF 属性的重要注意事项。</span><span class="sxs-lookup"><span data-stu-id="49202-112">The remainder of this section describes the structure and syntax of a TNEF stream, the mapping between MAPI properties and TNEF attributes, and important considerations for certain TNEF attributes.</span></span>
  

