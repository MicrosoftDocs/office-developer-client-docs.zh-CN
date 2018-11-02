---
title: onError 事件 (RDS)
TOCTitle: onError event (RDS)
ms:assetid: e26a3f7f-0f00-919a-65ad-bf39ffb83e92
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250153(v=office.15)
ms:contentKeyID: 48548292
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c67e277c35e3cf6c75226dc138aa4b288843e6bf
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930859"
---
# <a name="onerror-event-rds"></a><span data-ttu-id="fa62a-102">onError 事件 (RDS)</span><span class="sxs-lookup"><span data-stu-id="fa62a-102">onError event (RDS)</span></span>


<span data-ttu-id="fa62a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa62a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fa62a-104">只要在操作期间发生错误，便会调用 **onError** 事件。</span><span class="sxs-lookup"><span data-stu-id="fa62a-104">The **onError** event is called whenever an error occurs during an operation.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa62a-105">语法</span><span class="sxs-lookup"><span data-stu-id="fa62a-105">Syntax</span></span>

<span data-ttu-id="fa62a-106">onError*SCode*，*说明*，*源*， *CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="fa62a-106">onError*SCode*, *Description*, *Source*, *CancelDisplay*</span></span>

## <a name="parameters"></a><span data-ttu-id="fa62a-107">参数</span><span class="sxs-lookup"><span data-stu-id="fa62a-107">Parameters</span></span>

  - <span data-ttu-id="fa62a-108">*SCode*</span><span class="sxs-lookup"><span data-stu-id="fa62a-108">*SCode*</span></span>

  - <span data-ttu-id="fa62a-109">指示错误的状态代码的整数。</span><span class="sxs-lookup"><span data-stu-id="fa62a-109">An integer that indicates the status code of the error.</span></span>

  - <span data-ttu-id="fa62a-110">*Description*</span><span class="sxs-lookup"><span data-stu-id="fa62a-110">*Description*</span></span>

  - <span data-ttu-id="fa62a-111">**字符串型** ，指示错误的说明。</span><span class="sxs-lookup"><span data-stu-id="fa62a-111">A **String** that indicates a description of the error.</span></span>

  - <span data-ttu-id="fa62a-112">*Source*</span><span class="sxs-lookup"><span data-stu-id="fa62a-112">*Source*</span></span>

  - <span data-ttu-id="fa62a-113">**字符串型** ，指示导致错误的查询或命令。</span><span class="sxs-lookup"><span data-stu-id="fa62a-113">A **String** that indicates the query or command that caused the error.</span></span>

  - <span data-ttu-id="fa62a-114">*CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="fa62a-114">*CancelDisplay*</span></span>

  - <span data-ttu-id="fa62a-115">**Boolean** 值，如果设置为 **True** ，则禁止在对话框中显示错误。</span><span class="sxs-lookup"><span data-stu-id="fa62a-115">A **Boolean** value, which if set to **True**, that prevents the error from being displayed in a dialog box.</span></span>

