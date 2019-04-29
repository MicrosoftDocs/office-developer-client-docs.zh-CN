---
title: EXCHANGE_STORE_VERSION_NUM
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88950eda-85ae-ad7a-46c6-0e1933d35e04
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf60b12a6e4575d3504a112aa2b54fb8c4ae23c7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433722"
---
# <a name="exchangestoreversionnum"></a><span data-ttu-id="5ca41-103">EXCHANGE_STORE_VERSION_NUM</span><span class="sxs-lookup"><span data-stu-id="5ca41-103">EXCHANGE_STORE_VERSION_NUM</span></span>

  
  
<span data-ttu-id="5ca41-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ca41-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ca41-105">存储 microsoft Office Outlook 配置文件中的帐户连接到的 microsoft Exchange Server 的版本信息。</span><span class="sxs-lookup"><span data-stu-id="5ca41-105">Stores version information for the Microsoft Exchange Server that accounts in a Microsoft Office Outlook profile are connected to.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5ca41-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="5ca41-106">Quick info</span></span>

```cpp
typedef struct { 
    WORD wMajorVersion; 
    WORD wMinorVersion; 
    WORD wBuild; 
    WORD wMinorBuild; 
} EXCHANGE_STORE_VERSION_NUM; 

```

## <a name="members"></a><span data-ttu-id="5ca41-107">成员</span><span class="sxs-lookup"><span data-stu-id="5ca41-107">Members</span></span>

 <span data-ttu-id="5ca41-108">_wMajorVersion_</span><span class="sxs-lookup"><span data-stu-id="5ca41-108">_wMajorVersion_</span></span>
  
- <span data-ttu-id="5ca41-109">主版本号, 当版本中包含重要的新功能和功能更改时, 通常会增加该版本号。</span><span class="sxs-lookup"><span data-stu-id="5ca41-109">Major version number that is generally incremented when a release contains significant new features and changes in functionality.</span></span>
    
 <span data-ttu-id="5ca41-110">_wMinorVersion_</span><span class="sxs-lookup"><span data-stu-id="5ca41-110">_wMinorVersion_</span></span>
  
- <span data-ttu-id="5ca41-111">与特定主要版本号相对应且通常在发布包含次要新功能或重大修补程序时递增的次要版本号。</span><span class="sxs-lookup"><span data-stu-id="5ca41-111">Minor version number that corresponds to a specific major version number and that is generally incremented when a release contains minor new features or significant fixes.</span></span>
    
 <span data-ttu-id="5ca41-112">_wBuild_</span><span class="sxs-lookup"><span data-stu-id="5ca41-112">_wBuild_</span></span>
  
- <span data-ttu-id="5ca41-113">与特定主要和次要版本号相对应且在包含新功能或修补程序的内部版本中通常会递增的主要内部版本号。</span><span class="sxs-lookup"><span data-stu-id="5ca41-113">Major build number that corresponds to specific major and minor version numbers and that is generally incremented in an internal release that contains new features or fixes.</span></span> <span data-ttu-id="5ca41-114">当 release 是主要的内部代码分支或里程碑 (如候选发布) 时, 此值也会增加。</span><span class="sxs-lookup"><span data-stu-id="5ca41-114">This value is also incremented when the release is a major internal code branch or milestone, such as a release candidate.</span></span>
    
 <span data-ttu-id="5ca41-115">_wMinorBuild_</span><span class="sxs-lookup"><span data-stu-id="5ca41-115">_wMinorBuild_</span></span>
  
- <span data-ttu-id="5ca41-116">在内部版本中通常递增的次要内部版本号, 其中包含与表示主要代码分支或里程碑的特定主要版本对应的新功能或修补程序。</span><span class="sxs-lookup"><span data-stu-id="5ca41-116">Minor build number that is generally incremented in an internal release that contains new features or fixes corresponding to a specific major build that denotes a major code branch or milestone.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ca41-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ca41-117">See also</span></span>



[<span data-ttu-id="5ca41-118">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="5ca41-118">About MAPI Additions</span></span>](about-mapi-additions.md)
  
[<span data-ttu-id="5ca41-119">PidTagProfileServerFullVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ca41-119">PidTagProfileServerFullVersion Canonical Property</span></span>](pidtagprofileserverfullversion-canonical-property.md)

