---
title: EXCHANGE_STORE_VERSION_NUM
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88950eda-85ae-ad7a-46c6-0e1933d35e04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 00d92f8e2ec3af766d5b241d1a911be304b346d6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774886"
---
# <a name="exchangestoreversionnum"></a><span data-ttu-id="fbd82-103">EXCHANGE_STORE_VERSION_NUM</span><span class="sxs-lookup"><span data-stu-id="fbd82-103">EXCHANGE_STORE_VERSION_NUM</span></span>

  
  
<span data-ttu-id="fbd82-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fbd82-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fbd82-105">存储在 Microsoft Office Outlook 配置文件中的帐户连接到 Microsoft Exchange Server 版本信息。</span><span class="sxs-lookup"><span data-stu-id="fbd82-105">Stores version information for the Microsoft Exchange Server that accounts in a Microsoft Office Outlook profile are connected to.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="fbd82-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="fbd82-106">Quick info</span></span>

```cpp
typedef struct { 
    WORD wMajorVersion; 
    WORD wMinorVersion; 
    WORD wBuild; 
    WORD wMinorBuild; 
} EXCHANGE_STORE_VERSION_NUM; 

```

## <a name="members"></a><span data-ttu-id="fbd82-107">Members</span><span class="sxs-lookup"><span data-stu-id="fbd82-107">Members</span></span>

 <span data-ttu-id="fbd82-108">_wMajorVersion_</span><span class="sxs-lookup"><span data-stu-id="fbd82-108">_wMajorVersion_</span></span>
  
- <span data-ttu-id="fbd82-109">通常会增加，当发行版中包含大量新功能和更改功能的主要版本号。</span><span class="sxs-lookup"><span data-stu-id="fbd82-109">Major version number that is generally incremented when a release contains significant new features and changes in functionality.</span></span>
    
 <span data-ttu-id="fbd82-110">_wMinorVersion_</span><span class="sxs-lookup"><span data-stu-id="fbd82-110">_wMinorVersion_</span></span>
  
- <span data-ttu-id="fbd82-111">次要版本数字，对应于特定的主要版本号和发行版中包含次要的新功能或重要修复时通常递增。</span><span class="sxs-lookup"><span data-stu-id="fbd82-111">Minor version number that corresponds to a specific major version number and that is generally incremented when a release contains minor new features or significant fixes.</span></span>
    
 <span data-ttu-id="fbd82-112">_wBuild_</span><span class="sxs-lookup"><span data-stu-id="fbd82-112">_wBuild_</span></span>
  
- <span data-ttu-id="fbd82-113">对应于特定的主要和次要版本号码和，通常会递增在内部版本中包含的新功能或修补程序的主要内部版本号。</span><span class="sxs-lookup"><span data-stu-id="fbd82-113">Major build number that corresponds to specific major and minor version numbers and that is generally incremented in an internal release that contains new features or fixes.</span></span> <span data-ttu-id="fbd82-114">主要内部代码分支或里程碑，如候选发布版发行版时，还会递增此值。</span><span class="sxs-lookup"><span data-stu-id="fbd82-114">This value is also incremented when the release is a major internal code branch or milestone, such as a release candidate.</span></span>
    
 <span data-ttu-id="fbd82-115">_wMinorBuild_</span><span class="sxs-lookup"><span data-stu-id="fbd82-115">_wMinorBuild_</span></span>
  
- <span data-ttu-id="fbd82-116">通常会在内部版本中包含的新功能或修复对应于特定的主要生成表示主要代码分支或里程碑递增的次要版本号。</span><span class="sxs-lookup"><span data-stu-id="fbd82-116">Minor build number that is generally incremented in an internal release that contains new features or fixes corresponding to a specific major build that denotes a major code branch or milestone.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fbd82-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbd82-117">See also</span></span>



[<span data-ttu-id="fbd82-118">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="fbd82-118">About MAPI Additions</span></span>](about-mapi-additions.md)
  
[<span data-ttu-id="fbd82-119">PidTagProfileServerFullVersion 规范属性</span><span class="sxs-lookup"><span data-stu-id="fbd82-119">PidTagProfileServerFullVersion Canonical Property</span></span>](pidtagprofileserverfullversion-canonical-property.md)

