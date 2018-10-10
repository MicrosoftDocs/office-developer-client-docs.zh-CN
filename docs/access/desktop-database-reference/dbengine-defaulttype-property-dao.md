---
title: DBEngine.DefaultType Property (DAO)
TOCTitle: DefaultType Property
ms:assetid: b4371f3e-1ce0-1d0f-93a8-0c5329b510ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822060(v=office.15)
ms:contentKeyID: 48547217
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053580
f1_categories:
- Office.Version=v15
ms.openlocfilehash: d32c0860f76aeeaa64a060a55579d05c1eb571ab
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467499"
---
# <a name="dbenginedefaulttype-property-dao"></a><span data-ttu-id="5cd03-102">DBEngine.DefaultType Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="5cd03-102">DBEngine.DefaultType Property (DAO)</span></span>


<span data-ttu-id="5cd03-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5cd03-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5cd03-104">设置或返回一个值，该值指示下一个创建的 **[Workspace](workspace-object-dao.md)** 对象将要使用的工作区类型。</span><span class="sxs-lookup"><span data-stu-id="5cd03-104">Sets or returns a value that indicates what type of workspace will be used by the next **[Workspace](workspace-object-dao.md)** object created.</span></span>

## <a name="syntax"></a><span data-ttu-id="5cd03-105">语法</span><span class="sxs-lookup"><span data-stu-id="5cd03-105">Syntax</span></span>

<span data-ttu-id="5cd03-106">*表达式*。DefaultType</span><span class="sxs-lookup"><span data-stu-id="5cd03-106">*expression* .DefaultType</span></span>

<span data-ttu-id="5cd03-107">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="5cd03-107">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cd03-108">注解</span><span class="sxs-lookup"><span data-stu-id="5cd03-108">Remarks</span></span>

<span data-ttu-id="5cd03-109">该设置值或返回值可以是 **[WorkspaceTypeEnum](workspacetypeenum-enumeration-dao.md)** 常量之一。</span><span class="sxs-lookup"><span data-stu-id="5cd03-109">The setting or return value can be one of the of the **[WorkspaceTypeEnum](workspacetypeenum-enumeration-dao.md)** constants.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5cd03-110">Microsoft Access 2013 中不支持适用于 ODBCDirect 工作区。</span><span class="sxs-lookup"><span data-stu-id="5cd03-110">ODBCDirect workspaces are not supported in Microsoft Access 2013.</span></span> <span data-ttu-id="5cd03-111">如果要在不使用 Microsoft Access 数据库引擎的情况下访问外部数据源，请使用 ADO。</span><span class="sxs-lookup"><span data-stu-id="5cd03-111">Use ADO if you want to access external data sources without using the Microsoft Access database engine.</span></span></P>



<span data-ttu-id="5cd03-112">通过设置**[CreateWorkspace](dbengine-createworkspace-method-dao.md)** 方法的 type 参数可以为单个**工作区**中重写设置。</span><span class="sxs-lookup"><span data-stu-id="5cd03-112">The setting can be overridden for a single **Workspace** by setting the type argument to the **[CreateWorkspace](dbengine-createworkspace-method-dao.md)** method.</span></span>

