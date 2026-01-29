<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Fun Games Win Rewards</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
    -webkit-tap-highlight-color: transparent;
}

body {
    background: linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%);
    min-height: 100vh;
    width: 100%;
    color: #333;
    overflow-x: hidden;
    padding: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.app-container {
    width: 100%;
    max-width: 500px;
    min-height: 95vh;
    display: flex;
    flex-direction: column;
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border-radius: 25px;
    box-shadow: 
        0 10px 30px rgba(0, 0, 0, 0.1),
        0 1px 8px rgba(255, 255, 255, 0.3) inset;
    border: 1px solid rgba(255, 255, 255, 0.3);
    overflow: hidden;
}

/* HEADER */
.header {
    background: linear-gradient(135deg, 
        rgba(79, 195, 247, 0.85), 
        rgba(2, 136, 209, 0.85));
    padding: 40px 16px 20px;
    text-align: center;
    position: relative;
    overflow: hidden;
    width: 100%;
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    border-bottom: 1px solid rgba(255, 255, 255, 0.3);
}

.progress-top-section {
    position: absolute;
    top: 12px;
    left: 16px;
    right: 16px;
    z-index: 10;
}

.progress-wrap {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 0;
    width: 100%;
}

.progress-container {
    flex: 1;
    position: relative;
    min-width: 0;
}

.progress {
    height: 38px;
    background: rgba(0,0,0,0.08);
    border-radius: 19px;
    overflow: hidden;
    box-shadow: inset 0 2px 8px rgba(0,0,0,0.1);
    position: relative;
    border: 1px solid rgba(255,255,255,0.4);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    display: flex;
    align-items: center;
    padding: 0 12px;
}

.progress-bar {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    background: linear-gradient(90deg, 
        rgba(255, 167, 38, 0.8), 
        rgba(255, 152, 0, 0.7), 
        rgba(251, 140, 0, 0.6));
    width: 0%;
    transition: width 0.5s ease;
    z-index: 1;
}

.progress-content {
    position: relative;
    z-index: 2;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 3px;
}

.progress-text-group {
    display: flex;
    align-items: center;
    gap: 8px;
    flex: 1;
    min-width: 0;
    overflow: hidden;
    margin-right: 6px;
}

.progress-icon {
    color: rgba(255, 152, 0, 0.9);
    font-size: 13px;
    background: rgba(255, 255, 255, 0.25);
    width: 22px;
    height: 22px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
}

.progress-text {
    font-size: 11px;
    font-weight: 700;
    color: #333;
    text-shadow: 0 1px 2px rgba(255,255,255,0.8);
    letter-spacing: 0.2px;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    flex: 1;
    line-height: 1.1;
}

.redeem-btn {
    background: linear-gradient(135deg, 
        rgba(255, 152, 0, 0.85), 
        rgba(255, 87, 34, 0.8), 
        rgba(255, 152, 0, 0.85));
    color: #fff;
    padding: 4px 8px;
    border-radius: 12px;
    font-size: 10px;
    font-weight: 700;
    box-shadow: 0 3px 8px rgba(255, 87, 34, 0.25);
    border: none;
    cursor: pointer;
    transition: all 0.15s ease;
    white-space: nowrap;
    display: flex;
    align-items: center;
    gap: 3px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    height: 24px;
    flex-shrink: 0;
    min-width: 75px;
}

.redeem-btn:hover {
    transform: translateY(-1px);
    background: linear-gradient(135deg, 
        rgba(255, 87, 34, 0.9), 
        rgba(255, 152, 0, 0.9), 
        rgba(255, 87, 34, 0.9));
}

.redeem-btn:active {
    transform: translateY(0);
}

.daily-status {
    margin-top: 10px;
    padding: 8px 12px;
    background: rgba(255,255,255,0.2);
    border-radius: 12px;
    font-size: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: white;
    text-shadow: 0 1px 2px rgba(0,0,0,0.2);
    backdrop-filter: blur(5px);
    border: 1px solid rgba(255,255,255,0.1);
}

.daily-status i {
    margin-right: 6px;
    font-size: 11px;
}

/* Small Timer Display */
.small-timer {
    display: inline-block;
    font-size: 10px;
    font-weight: 700;
    background: rgba(255, 87, 34, 0.2);
    color: #FF5722;
    padding: 2px 6px;
    border-radius: 8px;
    margin-left: 8px;
    border: 1px solid rgba(255, 87, 34, 0.3);
    min-width: 60px;
    text-align: center;
    backdrop-filter: blur(5px);
}

.cycle-cooldown-timer {
    font-size: 9px;
    font-weight: 600;
    color: #FF9800;
    background: rgba(255, 152, 0, 0.1);
    padding: 1px 5px;
    border-radius: 6px;
    margin-left: 5px;
    border: 1px solid rgba(255, 152, 0, 0.2);
}

/* GAME AREA */
.game {
    background: linear-gradient(135deg, 
        rgba(161, 196, 253, 0.7), 
        rgba(194, 233, 251, 0.7));
    padding: 20px 16px;
    text-align: center;
    position: relative;
    flex: 1;
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.center-container {
    text-align: center;
    padding: 20px;
    width: 100%;
}

.main-title {
    font-size: 24px;
    font-weight: 800;
    color: #333;
    margin-bottom: 10px;
    text-shadow: 0 2px 4px rgba(255,255,255,0.8);
}

.sub-title {
    font-size: 16px;
    color: #666;
    margin-bottom: 30px;
    font-weight: 500;
}

.reward-container {
    background: rgba(255, 255, 255, 0.15);
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    border-radius: 20px;
    padding: 25px 20px;
    margin-bottom: 25px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    box-shadow: 
        0 8px 20px rgba(0, 0, 0, 0.1),
        0 1px 3px rgba(255, 255, 255, 0.5) inset;
}

.reward-amount {
    font-size: 32px;
    font-weight: 800;
    color: #FF9800;
    margin-bottom: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
    text-shadow: 0 2px 4px rgba(0,0,0,0.2);
}

.coin-icon-large {
    color: #FFD700;
    font-size: 28px;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.3));
}

.draw-stats {
    display: flex;
    justify-content: space-around;
    margin-top: 25px;
    font-size: 14px;
}

.stat-item {
    text-align: center;
    padding: 10px;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 12px;
    min-width: 80px;
    border: 1px solid rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
}

.stat-label {
    color: #666;
    font-size: 12px;
    margin-bottom: 5px;
    font-weight: 600;
}

.stat-value {
    color: #333;
    font-weight: 800;
    font-size: 18px;
    text-shadow: 0 1px 2px rgba(255,255,255,0.8);
}

.ads-timer-display {
    font-size: 14px;
    font-weight: 600;
    background: rgba(0, 0, 0, 0.2);
    padding: 10px 20px;
    border-radius: 15px;
    border: 1px solid rgba(255, 255, 255, 0.2);
    min-width: 120px;
    text-align: center;
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    margin: 20px auto;
    display: inline-block;
}

.draw-btn {
    background: linear-gradient(135deg, 
        rgba(79, 195, 247, 0.85), 
        rgba(2, 136, 209, 0.85));
    color: #fff;
    border: none;
    padding: 18px 30px;
    border-radius: 30px;
    font-size: 18px;
    font-weight: 700;
    margin-top: 20px;
    cursor: pointer;
    box-shadow: 
        0 8px 20px rgba(79, 195, 247, 0.2),
        0 4px 8px rgba(255, 255, 255, 0.2) inset;
    transition: all 0.15s ease;
    position: relative;
    width: 100%;
    max-width: 280px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 12px;
    text-shadow: 0 1px 2px rgba(0,0,0,0.2);
}

.draw-btn:hover:not(:disabled) {
    transform: translateY(-2px);
    box-shadow: 
        0 10px 25px rgba(79, 195, 247, 0.3),
        0 4px 8px rgba(255, 255, 255, 0.2) inset;
}

.draw-btn:active:not(:disabled) {
    transform: translateY(0);
}

.draw-btn:disabled {
    background: linear-gradient(135deg, 
        rgba(158, 158, 158, 0.7), 
        rgba(117, 117, 117, 0.7));
    cursor: not-allowed;
    opacity: 0.8;
    box-shadow: none;
}

/* DAYS - SCROLLABLE CONTAINER */
.days-scroll-container {
    margin: 8px 12px;
    position: relative;
    border-radius: 20px;
    overflow: hidden;
    min-height: 140px;
}

.days-container {
    padding: 20px 16px;
    background: rgba(255, 255, 255, 0.75);
    backdrop-filter: blur(25px);
    -webkit-backdrop-filter: blur(25px);
    border-top: 1px solid rgba(255, 255, 255, 0.4);
    border-bottom: 1px solid rgba(255, 255, 255, 0.4);
    border-radius: 20px;
    box-shadow: 
        0 5px 15px rgba(0, 0, 0, 0.05),
        0 1px 3px rgba(255, 255, 255, 0.5) inset;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    scrollbar-width: thin;
    scrollbar-color: rgba(79, 195, 247, 0.5) rgba(255, 255, 255, 0.3);
    position: relative;
    min-height: 140px;
}

.days-container::-webkit-scrollbar {
    height: 6px;
}

.days-container::-webkit-scrollbar-track {
    background: rgba(255, 255, 255, 0.3);
    border-radius: 3px;
}

.days-container::-webkit-scrollbar-thumb {
    background: rgba(79, 195, 247, 0.5);
    border-radius: 3px;
}

.days-container::-webkit-scrollbar-thumb:hover {
    background: rgba(79, 195, 247, 0.7);
}

.days-title {
    font-size: 16px;
    font-weight: 600;
    color: #333;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
    text-shadow: 0 1px 1px rgba(255,255,255,0.5);
    position: sticky;
    left: 0;
    top: 0;
    background: rgba(255, 255, 255, 0.9);
    padding: 8px 0;
    border-radius: 10px;
    z-index: 1;
    backdrop-filter: blur(10px);
}

.days-title i {
    color: #4FC3F7;
    background: rgba(79, 195, 247, 0.1);
    padding: 8px;
    border-radius: 50%;
    font-size: 14px;
    flex-shrink: 0;
}

.days-scroll-wrapper {
    display: inline-flex;
    gap: 6px;
    padding-bottom: 5px;
    min-width: min-content;
}

/* Day item */
.day {
    width: 52px;
    min-width: 52px;
    background: linear-gradient(135deg, 
        rgba(79, 195, 247, 0.85), 
        rgba(2, 136, 209, 0.85));
    border-radius: 12px;
    padding: 10px 0;
    font-size: 10px;
    text-align: center;
    box-shadow: 0 3px 8px rgba(3, 155, 229, 0.15);
    transition: all 0.15s ease;
    cursor: pointer;
    position: relative;
    overflow: hidden;
    color: white;
    font-weight: 600;
    border: 1px solid rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    flex-shrink: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.day:hover:not(.claimed):not(.future) {
    transform: translateY(-2px);
}

.day.today {
    background: linear-gradient(135deg, 
        rgba(0, 200, 83, 0.9), 
        rgba(0, 230, 118, 0.9));
    border: 1px solid rgba(255, 255, 255, 0.35);
}

.day.claimed {
    background: linear-gradient(135deg, 
        rgba(0, 200, 83, 0.6), 
        rgba(0, 230, 118, 0.6));
    color: white;
    cursor: default;
}

.day.future {
    background: linear-gradient(135deg, 
        rgba(158, 158, 158, 0.6), 
        rgba(117, 117, 117, 0.6));
    color: rgba(255, 255, 255, 0.7);
    cursor: not-allowed;
    opacity: 0.7;
}

.day.today::after {
    content: "⏰";
    position: absolute;
    top: -6px;
    right: -6px;
    background: #FF9800;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    font-size: 9px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    z-index: 2;
}

.day.claimed::after {
    content: "✓";
    position: absolute;
    top: -6px;
    right: -6px;
    background: #00C853;
    width: 18px;
    height: 18px;
    border-radius: 50%;
    font-size: 10px;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid white;
    box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    z-index: 2;
}

.day-value {
    font-weight: 800;
    font-size: 11px;
    margin-top: 4px;
    text-shadow: 0 1px 2px rgba(0,0,0,0.2);
    letter-spacing: 0.3px;
}

.next-claim-timer {
    font-size: 8px;
    margin-top: 2px;
    opacity: 0.9;
    font-weight: 600;
    background: rgba(0, 0, 0, 0.2);
    padding: 2px 4px;
    border-radius: 6px;
    width: 90%;
}

/* Simple Notification */
.simple-notification {
    position: fixed;
    top: 20px;
    left: 50%;
    transform: translateX(-50%) translateY(-20px);
    background: rgba(255, 255, 255, 0.95);
    color: #333;
    padding: 12px 20px;
    border-radius: 15px;
    font-size: 14px;
    font-weight: 600;
    z-index: 1000;
    opacity: 0;
    transition: all 0.3s ease;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.15);
    border: 1px solid rgba(255, 255, 255, 0.5);
    text-align: center;
    max-width: 300px;
    pointer-events: none;
    border-left: 4px solid #4CAF50;
}

.simple-notification.show {
    opacity: 1;
    transform: translateX(-50%) translateY(0);
}

.simple-notification.error {
    border-left-color: #FF5722;
}

.simple-notification.info {
    border-left-color: #2196F3;
}

.notification-text {
    display: flex;
    align-items: center;
    gap: 8px;
    justify-content: center;
}

.notification-coins {
    color: #FF9800;
    font-weight: 700;
    margin-left: 4px;
}

/* Incomplete Ad Overlay */
.incomplete-ad-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.95);
    z-index: 4000;
    display: none;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: center;
    padding: 20px;
}

.incomplete-ad-overlay.active {
    display: flex;
}

.incomplete-ad-content {
    max-width: 400px;
    width: 100%;
    background: rgba(255, 255, 255, 0.1);
    border-radius: 20px;
    padding: 30px;
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
}

.remaining-seconds {
    font-size: 48px;
    font-weight: 800;
    color: #FF5722;
    margin: 20px 0;
    text-shadow: 0 0 15px rgba(255, 87, 34, 0.7);
}

.resume-btn {
    background: linear-gradient(135deg, #FF5722, #FF9800);
    color: white;
    border: none;
    padding: 15px 30px;
    border-radius: 25px;
    font-size: 18px;
    font-weight: 700;
    margin-top: 20px;
    cursor: pointer;
    transition: all 0.15s ease;
    width: 100%;
    max-width: 280px;
    border: 1px solid rgba(255, 255, 255, 0.3);
    backdrop-filter: blur(10px);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}

.resume-btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 20px rgba(255, 87, 34, 0.3);
}

.resume-btn:active {
    transform: translateY(0);
}

.incomplete-message {
    font-size: 16px;
    margin-bottom: 20px;
    color: #ddd;
    line-height: 1.5;
    background: rgba(255, 87, 34, 0.1);
    padding: 15px;
    border-radius: 10px;
    border: 1px solid rgba(255, 87, 34, 0.3);
}

.warning-message {
    color: #FF5722;
    font-size: 14px;
    margin-top: 20px;
    padding: 12px;
    background: rgba(255, 87, 34, 0.1);
    border-radius: 10px;
    border: 1px solid rgba(255, 87, 34, 0.3);
}

/* 출금 모달 */
.redeem-options-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.9);
    z-index: 2000;
    display: flex;
    justify-content: center;
    align-items: center;
    opacity: 0;
    visibility: hidden;
    transition: opacity 0.2s ease, visibility 0.2s ease;
}

.redeem-options-overlay.active {
    opacity: 1;
    visibility: visible;
}

.redeem-options-modal {
    background: white;
    border-radius: 25px;
    width: 92%;
    max-width: 420px;
    padding: 25px 20px;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.4);
    position: relative;
    overflow: hidden;
    max-height: 85vh;
    overflow-y: auto;
    transform: scale(0.95);
    transition: transform 0.2s ease;
}

.redeem-options-overlay.active .redeem-options-modal {
    transform: scale(1);
}

.redeem-modal-header {
    text-align: center;
    margin-bottom: 20px;
    padding-bottom: 15px;
    border-bottom: 2px solid rgba(255, 152, 0, 0.2);
}

.redeem-modal-header h3 {
    color: #333;
    font-size: 22px;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    font-weight: 700;
}

.redeem-modal-header h3 i {
    color: #FF9800;
    font-size: 24px;
}

.redeem-subtitle {
    color: #666;
    font-size: 14px;
    font-weight: 500;
    background: #fff8e1;
    padding: 6px 12px;
    border-radius: 10px;
    display: inline-block;
    border: 1px solid #ffecb3;
}

/* 코인 상태 표시 */
.coin-status-container {
    background: #fff8e1;
    border-radius: 15px;
    padding: 20px;
    margin-bottom: 20px;
    border: 2px solid #ffecb3;
    transition: opacity 0.2s ease;
}

.coin-amount-display {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: white;
    border-radius: 12px;
    padding: 15px;
    border: 2px solid #ffecb3;
    margin-top: 15px;
}

.current-amount, .required-amount {
    text-align: center;
    flex: 1;
}

.amount-label {
    color: #666;
    font-size: 12px;
    font-weight: 600;
    margin-bottom: 5px;
    display: block;
}

.amount-value {
    font-size: 18px;
    font-weight: 700;
    color: #333;
}

.current-amount .amount-value {
    color: #2196F3;
}

.required-amount .amount-value {
    color: #4CAF50;
}

.coin-difference {
    text-align: center;
    margin-top: 15px;
    padding: 10px;
    border-radius: 10px;
    font-weight: 600;
    font-size: 14px;
}

.coin-difference.enough {
    background: #e8f5e9;
    color: #2E7D32;
    border: 2px solid #c8e6c9;
}

.coin-difference.not-enough {
    background: #fff3e0;
    color: #FF5722;
    border: 2px dashed #ffcc80;
}

/* 결제 옵션 컨테이너 */
.payment-options-container {
    margin-bottom: 25px;
    transition: opacity 0.2s ease;
}

.payment-options-title {
    color: #333;
    font-size: 16px;
    font-weight: 600;
    margin-bottom: 15px;
    text-align: center;
}

.payment-options-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 15px;
}

.payment-option-simple {
    background: white;
    border-radius: 15px;
    padding: 20px 15px;
    cursor: pointer;
    transition: all 0.15s ease;
    border: 2px solid #e0e0e0;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.payment-option-simple:hover {
    transform: translateY(-3px);
    border-color: #2196F3;
}

.payment-icon-simple {
    width: 60px;
    height: 60px;
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 10px;
    background: white;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 8px;
    border: 2px solid #f5f5f5;
}

.payment-icon-simple img {
    width: 100%;
    height: 100%;
    object-fit: contain;
}

.payment-name-simple {
    color: #333;
    font-size: 16px;
    font-weight: 600;
    margin-top: 5px;
}

/* 결제 세부 정보 */
.selected-payment-details {
    background: white;
    border-radius: 20px;
    padding: 20px;
    margin-top: 0;
    margin-bottom: 20px;
    border: 2px solid #e0e0e0;
    display: none;
    opacity: 0;
    transform: translateY(10px);
    transition: opacity 0.2s ease, transform 0.2s ease;
}

.selected-payment-details.active {
    display: block;
    opacity: 1;
    transform: translateY(0);
}

.selected-method-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 25px;
    padding-bottom: 20px;
    border-bottom: 2px solid #f5f5f5;
}

.back-button {
    background: none;
    color: #666;
    border: none;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.15s ease;
    display: flex;
    align-items: center;
    justify-content: center;
}

.back-button:hover {
    background: #f5f5f5;
}

.selected-method-title {
    flex: 1;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
}

.method-icon {
    width: 30px;
    height: 30px;
    border-radius: 8px;
    overflow: hidden;
    border: 2px solid #f5f5f5;
}

.method-name {
    font-weight: 700;
    color: #333;
    font-size: 16px;
}

.amount-display {
    background: #FF9800;
    color: white;
    padding: 8px 16px;
    border-radius: 20px;
    font-weight: 700;
    font-size: 16px;
    border: 2px solid #FF9800;
    min-width: 120px;
    text-align: center;
}

/* 입력 그룹 */
.input-group {
    margin-bottom: 25px;
}

.input-group label {
    display: block;
    color: #444;
    font-size: 14px;
    font-weight: 600;
    margin-bottom: 8px;
    padding-left: 5px;
}

.input-group input {
    width: 100%;
    padding: 14px 16px;
    border-radius: 12px;
    border: 2px solid #e0e0e0;
    font-size: 15px;
    transition: border-color 0.15s ease;
    background: white;
    color: #333;
}

.input-group input:focus {
    outline: none;
    border-color: #2196F3;
    box-shadow: 0 0 0 3px rgba(33, 150, 243, 0.1);
}

.input-group input::placeholder {
    color: #999;
}

/* 출금 정보 */
.withdraw-note {
    background: #e3f2fd;
    border-radius: 12px;
    padding: 15px;
    margin-top: 25px;
    display: flex;
    gap: 12px;
    align-items: flex-start;
    border-left: 4px solid #2196F3;
}

.withdraw-note i {
    color: #2196F3;
    font-size: 20px;
    margin-top: 2px;
    flex-shrink: 0;
}

.withdraw-note p {
    color: #37474F;
    font-size: 13px;
    margin: 0;
    line-height: 1.4;
    font-weight: 500;
}

/* 모달 액션 버튼 */
.redeem-modal-actions {
    display: flex;
    gap: 15px;
    margin-top: 20px;
}

.modal-btn {
    flex: 1;
    padding: 16px;
    border-radius: 15px;
    font-size: 16px;
    font-weight: 600;
    border: none;
    cursor: pointer;
    transition: all 0.15s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.cancel-btn {
    background: #f5f5f5;
    color: #666;
    border: 2px solid #e0e0e0;
}

.cancel-btn:hover {
    background: #e0e0e0;
    transform: translateY(-1px);
}

.confirm-btn {
    background: linear-gradient(135deg, #4CAF50, #2E7D32);
    color: white;
    border: 2px solid #4CAF50;
}

.confirm-btn:hover:not(:disabled) {
    background: linear-gradient(135deg, #66BB6A, #388E3C);
    transform: translateY(-1px);
}

.confirm-btn:disabled {
    background: #bdbdbd;
    border-color: #9e9e9e;
    cursor: not-allowed;
    opacity: 0.7;
}

/* 로딩 화면 */
.loading-screen {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: linear-gradient(135deg, #a1c4fd 0%, #c2e9fb 100%);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    z-index: 2000;
    opacity: 1;
    transition: opacity 0.3s ease;
}

.loading-screen.hidden {
    opacity: 0;
    visibility: hidden;
}

.loading-logo {
    font-size: 32px;
    color: #0288D1;
    font-weight: 800;
    margin-bottom: 20px;
}

.loading-bar {
    width: 200px;
    height: 8px;
    background: rgba(255,255,255,0.3);
    border-radius: 4px;
    overflow: hidden;
    margin-bottom: 15px;
    border: 1px solid rgba(255, 255, 255, 0.2);
}

.loading-progress {
    width: 0%;
    height: 100%;
    background: linear-gradient(90deg, #4FC3F7, #0288D1);
    border-radius: 4px;
    transition: width 0.2s ease;
}

.loading-text {
    color: #0288D1;
    font-size: 12px;
    font-weight: 600;
}

/* 모바일 최적화 */
@media (max-width: 480px) {
    .app-container {
        max-width: 100%;
        border-radius: 20px;
        margin: 5px;
        min-height: 90vh;
    }
    
    .main-title {
        font-size: 20px;
    }
    
    .sub-title {
        font-size: 14px;
    }
    
    .reward-amount {
        font-size: 24px;
    }
    
    .progress {
        height: 32px;
        padding: 0 10px;
    }
    
    .progress-text {
        font-size: 10px;
    }
    
    .progress-icon {
        font-size: 12px;
        width: 20px;
        height: 20px;
    }
    
    .redeem-btn {
        padding: 3px 6px;
        font-size: 9px;
        height: 22px;
        border-radius: 10px;
        min-width: 70px;
    }
    
    .draw-btn {
        padding: 16px 24px;
        font-size: 16px;
        max-width: 90%;
    }
    
    .ads-timer-display {
        font-size: 12px;
        min-width: 80px;
        padding: 8px 16px;
    }
    
    .day {
        width: 48px;
        min-width: 48px;
        font-size: 9px;
        padding: 8px 0;
    }
    
    .day-value {
        font-size: 10px;
    }
    
    .days-container {
        margin: 8px;
        padding: 16px 12px;
        min-height: 130px;
    }
    
    .header {
        padding: 36px 16px 20px;
    }
    
    .next-claim-timer {
        font-size: 7px;
    }
    
    .simple-notification {
        max-width: 85%;
        padding: 10px 16px;
        font-size: 12px;
        top: 15px;
    }
    
    .notification-text {
        gap: 6px;
    }
    
    .stat-item {
        min-width: 70px;
        padding: 8px;
    }
    
    .stat-value {
        font-size: 16px;
    }
    
    .stat-label {
        font-size: 10px;
    }
    
    .redeem-options-modal {
        padding: 20px 15px;
        max-width: 95%;
        border-radius: 20px;
    }
    
    .redeem-modal-header h3 {
        font-size: 20px;
    }
    
    .redeem-subtitle {
        font-size: 13px;
    }
    
    .payment-option-simple {
        padding: 15px 10px;
    }
    
    .payment-icon-simple {
        width: 50px;
        height: 50px;
    }
    
    .payment-name-simple {
        font-size: 14px;
    }
    
    .modal-btn {
        padding: 14px;
        font-size: 14px;
    }
    
    .amount-display {
        min-width: 100px;
        padding: 6px 12px;
        font-size: 14px;
    }
    
    .coin-amount-display {
        padding: 12px;
    }
    
    .amount-value {
        font-size: 16px;
    }
    
    .input-group input {
        padding: 12px 14px;
        font-size: 14px;
    }
    
    .withdraw-note {
        padding: 12px;
        margin-top: 20px;
    }
    
    .withdraw-note p {
        font-size: 12px;
    }
    
    .selected-payment-details {
        padding: 16px;
        margin-top: 0;
    }
    
    .payment-options-grid {
        gap: 10px;
    }
    
    /* Incomplete Ad Mobile */
    .remaining-seconds {
        font-size: 36px;
    }
    
    .resume-btn {
        padding: 12px 24px;
        font-size: 16px;
    }
    
    .incomplete-message {
        font-size: 14px;
    }
    
    .warning-message {
        font-size: 12px;
    }
    
    .daily-status {
        font-size: 10px;
        padding: 6px 10px;
    }
    
    .small-timer {
        font-size: 9px;
        padding: 1px 4px;
        min-width: 50px;
        margin-left: 5px;
    }
    
    .cycle-cooldown-timer {
        font-size: 8px;
        padding: 1px 3px;
        margin-left: 3px;
    }
}

/* 태블릿 최적화 */
@media (min-width: 768px) {
    .app-container {
        max-width: 500px;
        margin: 20px auto;
        min-height: calc(100vh - 40px);
        max-height: 900px;
    }
    
    .day {
        width: 56px;
        min-width: 56px;
    }
}
</style>
</head>

<body>
    <!-- 로딩 화면 -->
    <div class="loading-screen" id="loadingScreen">
        <div class="loading-logo">Fun Games</div>
        <div class="loading-bar">
            <div class="loading-progress" id="loadingProgress"></div>
        </div>
        <div class="loading-text" id="loadingText">Loading...</div>
    </div>

    <!-- Simple Notification -->
    <div class="simple-notification" id="simpleNotification">
        <div class="notification-text">
            <i class="fas fa-check-circle"></i>
            <span id="notificationMessage">+150 Coins Added!</span>
            <span class="notification-coins" id="notificationAmount">150</span>
        </div>
    </div>

    <!-- Incomplete Ad Overlay -->
    <div class="incomplete-ad-overlay" id="incompleteAdOverlay">
        <div class="incomplete-ad-content">
            <div class="ads-title">ADVERTISEMENT INCOMPLETE</div>
            <div class="remaining-seconds" id="remainingSeconds">10</div>
            <div class="incomplete-message">
                You closed the advertisement too early! You need to watch the full 15 seconds to receive coins.
            </div>
            <button class="resume-btn" id="resumeAdBtn">
                <i class="fas fa-redo"></i> Watch Remaining <span id="watchSeconds">10</span> Seconds
            </button>
            <div class="warning-message">
                <i class="fas fa-exclamation-triangle"></i>
                If you close this screen, you will lose your progress for this ad.
            </div>
        </div>
    </div>

    <div class="app-container">
        <!-- Header -->
        <div class="header">
            <!-- Progress Bar -->
            <div class="progress-top-section">
                <div class="progress-wrap">
                    <div class="progress-container">
                        <div class="progress">
                            <div class="progress-bar" id="progressBar"></div>
                            <div class="progress-content">
                                <div class="progress-text-group">
                                    <div class="progress-icon">
                                        <i class="fas fa-coins"></i>
                                    </div>
                                    <span class="progress-text" id="progressText">0/1,000,000 (ks 600,000)</span>
                                </div>
                                <button class="redeem-btn" id="redeemBtn" onclick="showRedeemOptions()">
                                    <i class="fas fa-gift"></i> Redeem
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Daily Status -->
                <div class="daily-status">
                    <div>
                        <i class="fas fa-calendar-day"></i>
                        <span id="currentDate">Today: May 10</span>
                    </div>
                    <div>
                        <i class="fas fa-sync-alt"></i>
                        <span id="nextReset">Reset: 00:00</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Game Area -->
        <div class="game">
            <div class="center-container">
                <div class="main-title">WATCH & EARN</div>
                <div class="sub-title">Watch ads to collect coins</div>
                
                <div class="reward-container">
                    <div class="reward-amount">
                        <i class="fas fa-coins coin-icon-large"></i>
                        <span>150 Coins per Ad</span>
                    </div>
                    
                    <div class="draw-stats">
                        <div class="stat-item">
                            <div class="stat-label">Today's Ads</div>
                            <div class="stat-value" id="todayAdsCount">0</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-label">Current Cycle</div>
                            <div class="stat-value" id="currentCycle">1/3</div>
                        </div>
                        <div class="stat-item">
                            <div class="stat-label">Total Ads</div>
                            <div class="stat-value" id="totalAdsCount">0</div>
                        </div>
                    </div>
                    
                    <div class="ads-timer-display" id="adsTimerDisplay">
                        <span id="adsStatusText">0/100</span>
                    </div>
                </div>
                
                <button class="draw-btn" id="drawBtn" onclick="startAdWatch()">
                    <i class="fas fa-play-circle"></i> Watch Ad Now 
                </button>
            </div>
        </div>

        <!-- Days - 24hr Claim System -->
        <div class="days-scroll-container">
            <div class="days-container" id="daysContainer">
                <div class="days-title">
                    <i class="fas fa-calendar-alt"></i> Daily Rewards (24hr System)
                </div>
                <div class="days-scroll-wrapper" id="daysScrollWrapper">
                    <!-- Days will be generated by JavaScript -->
                </div>
            </div>
        </div>
    </div>

<script>
// Game variables
let coins = 0;
const maxCoins = 1000000;
const ksValue = 600000;

// Draw Now (Ad Watch) System
const AD_REWARD = 150; // Each ad gives 150 coins
const AD_DURATION = 15; // 15 seconds ad duration
const MAX_ADS_PER_CYCLE = 100; // တစ် cycle ကို 100 ads
const TOTAL_CYCLES = 3; // 3 cycles (300 ads total per day)
const CYCLE_COOLDOWN = 30 * 60 * 1000; // 30 minutes between cycles 1 and 2
const FINAL_CYCLE_COOLDOWN = 12 * 60 * 60 * 1000; // 12 hours after 3rd cycle

// Variables for ad system
let totalAdsWatched = 0;
let todayAdsWatched = 0;
let currentCycle = 1;
let lastAdTime = null;
let cycleStartTime = null;
let adsInCurrentCycle = 0;
let lastResetDate = null; // နောက်ဆုံး reset လုပ်တဲ့ရက်စွဲ

// Ad monitoring variables
let adStartTime = null;
let adWatchedSeconds = 0;
let adTimer = null;
let isAdInProgress = false;
let remainingSeconds = AD_DURATION;
let adTab = null;

// 24hr Daily Claim System
let lastClaimTime = null;
let currentDayIndex = 0;
const totalDays = 30;
const dayRewards = [
    2800, 3800, 4800, 5800, 6800, 7800, 8800, 9800, 10800, 11800,
    12800, 13800, 14800, 15800, 16800, 17800, 18800, 19800, 20800, 21800,
    22800, 23800, 24800, 25800, 26800, 27800, 28800, 29800, 30800, 31800
];

let claimedDays = [];

// စနစ်စတင်ချိန်
window.addEventListener('load', function() {
    loadGameData();
    
    const loadingScreen = document.getElementById('loadingScreen');
    const loadingProgress = document.getElementById('loadingProgress');
    const loadingText = document.getElementById('loadingText');
    
    let progress = 0;
    const loadingInterval = setInterval(() => {
        progress += 10;
        loadingProgress.style.width = `${progress}%`;
        
        if (progress <= 30) {
            loadingText.textContent = "Loading assets...";
        } else if (progress <= 60) {
            loadingText.textContent = "Initializing game...";
        } else if (progress <= 90) {
            loadingText.textContent = "Preparing UI...";
        } else {
            loadingText.textContent = "Ready to play!";
        }
        
        if (progress >= 100) {
            clearInterval(loadingInterval);
            setTimeout(() => {
                loadingScreen.classList.add('hidden');
                setTimeout(() => {
                    loadingScreen.style.display = 'none';
                    initializeResetSystem();
                    updateAdSystem();
                    generateDays();
                    updateProgress();
                    updateClaimTimers();
                    updateDrawButton();
                    updateDateDisplay();
                }, 300);
            }, 300);
        }
    }, 100);
});

// Load saved data
function loadGameData() {
    const savedCoins = localStorage.getItem('funGamesCoins');
    const savedTotalAds = localStorage.getItem('funGamesTotalAds');
    const savedTodayAds = localStorage.getItem('funGamesTodayAds');
    const savedCurrentCycle = localStorage.getItem('funGamesCurrentCycle');
    const savedAdsInCycle = localStorage.getItem('funGamesAdsInCycle');
    const savedCycleStart = localStorage.getItem('funGamesCycleStart');
    const savedLastAdTime = localStorage.getItem('funGamesLastAdTime');
    const savedLastClaim = localStorage.getItem('funGamesLastClaim');
    const savedClaimedDays = localStorage.getItem('funGamesClaimedDays');
    const savedCurrentDay = localStorage.getItem('funGamesCurrentDay');
    const savedLastReset = localStorage.getItem('funGamesLastReset');
    
    if (savedCoins) coins = parseInt(savedCoins);
    if (savedTotalAds) totalAdsWatched = parseInt(savedTotalAds);
    if (savedTodayAds) todayAdsWatched = parseInt(savedTodayAds);
    if (savedCurrentCycle) currentCycle = parseInt(savedCurrentCycle);
    if (savedAdsInCycle) adsInCurrentCycle = parseInt(savedAdsInCycle);
    if (savedCycleStart) cycleStartTime = parseInt(savedCycleStart);
    if (savedLastAdTime) lastAdTime = parseInt(savedLastAdTime);
    if (savedLastClaim) lastClaimTime = parseInt(savedLastClaim);
    if (savedClaimedDays) claimedDays = JSON.parse(savedClaimedDays);
    if (savedCurrentDay) currentDayIndex = parseInt(savedCurrentDay);
    if (savedLastReset) lastResetDate = savedLastReset;
}

// Save game data
function saveGameData() {
    localStorage.setItem('funGamesCoins', coins);
    localStorage.setItem('funGamesTotalAds', totalAdsWatched);
    localStorage.setItem('funGamesTodayAds', todayAdsWatched);
    localStorage.setItem('funGamesCurrentCycle', currentCycle);
    localStorage.setItem('funGamesAdsInCycle', adsInCurrentCycle);
    localStorage.setItem('funGamesCycleStart', cycleStartTime);
    localStorage.setItem('funGamesLastAdTime', lastAdTime);
    localStorage.setItem('funGamesLastClaim', lastClaimTime);
    localStorage.setItem('funGamesClaimedDays', JSON.stringify(claimedDays));
    localStorage.setItem('funGamesCurrentDay', currentDayIndex);
    localStorage.setItem('funGamesLastReset', lastResetDate);
}

// Daily Reset System ကို စတင်ခြင်း
function initializeResetSystem() {
    const now = new Date();
    const today = now.toDateString(); // "Mon May 10 2024"
    
    // ပထမဆုံးအကြိမ်လား စစ်ဆေး
    if (!lastResetDate) {
        lastResetDate = today;
        // Initialize cycle start time
        cycleStartTime = Date.now();
        saveGameData();
        return;
    }
    
    // နေ့သစ်ရောက်ပြီလား စစ်ဆေး
    if (lastResetDate !== today) {
        // နေ့သစ်ရောက်ပြီ - RESET လုပ်မယ်
        performDailyReset();
    }
}

// Daily Reset လုပ်ခြင်း
function performDailyReset() {
    const now = new Date();
    const today = now.toDateString();
    
    console.log(`Daily Reset: ${lastResetDate} → ${today}`);
    
    // RESET လုပ်ရမယ့် data များ
    todayAdsWatched = 0;
    currentCycle = 1;
    adsInCurrentCycle = 0;
    cycleStartTime = Date.now();
    lastAdTime = null;
    lastResetDate = today;
    
    saveGameData();
    
    // User ကိုပြော
    showSimpleNotification("New day started! Cycle reset to 1/3", "info");
    
    // UI update
    updateAdSystem();
    updateProgress();
}

// နေ့စဉ်စစ်ဆေးခြင်း (အလိုအလျောက်)
function checkDailyReset() {
    const now = new Date();
    const today = now.toDateString();
    
    if (lastResetDate && lastResetDate !== today) {
        performDailyReset();
    }
}

// Next reset time calculation
function getNextResetTime() {
    const now = new Date();
    const tomorrow = new Date(now);
    tomorrow.setDate(tomorrow.getDate() + 1);
    tomorrow.setHours(0, 0, 0, 0);
    return tomorrow.getTime();
}

// Update ad system status
function updateAdSystem() {
    const now = Date.now();
    
    // နေ့စဉ်စစ်ဆေးခြင်း
    checkDailyReset();
    
    // Update display
    document.getElementById('todayAdsCount').textContent = `${todayAdsWatched}`;
    document.getElementById('currentCycle').textContent = `${currentCycle}/${TOTAL_CYCLES}`;
    document.getElementById('totalAdsCount').textContent = totalAdsWatched;
    
    // Remove existing timers
    removeTimers();
    
    // Show current cycle progress
    document.getElementById('adsStatusText').textContent = `${adsInCurrentCycle}/${MAX_ADS_PER_CYCLE}`;
    
    // Check if current cycle is completed
    if (adsInCurrentCycle >= MAX_ADS_PER_CYCLE) {
        if (currentCycle < TOTAL_CYCLES) {
            // Cycle 1 or 2 completed - need to wait 30 minutes for next cycle
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd >= CYCLE_COOLDOWN) {
                // 30 minutes passed, can move to next cycle
                document.getElementById('adsStatusText').textContent = "Ready for next cycle";
                document.getElementById('adsTimerDisplay').style.background = "rgba(0, 200, 83, 0.3)";
            } else {
                // Still in cooldown
                const timeLeft = CYCLE_COOLDOWN - timeSinceLastAd;
                const minutes = Math.floor(timeLeft / (60 * 1000));
                const seconds = Math.floor((timeLeft % (60 * 1000)) / 1000);
                document.getElementById('adsStatusText').textContent = `Next cycle in: ${minutes}m ${seconds}s`;
                document.getElementById('adsTimerDisplay').style.background = "rgba(255, 87, 34, 0.3)";
            }
        } else if (currentCycle >= TOTAL_CYCLES) {
            // Cycle 3 completed - need to wait 12 hours or next day
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : FINAL_CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd >= FINAL_CYCLE_COOLDOWN) {
                // 12 hours passed
                document.getElementById('adsStatusText').textContent = "Ready for next day";
                document.getElementById('adsTimerDisplay').style.background = "rgba(0, 200, 83, 0.3)";
            } else {
                // Still in cooldown
                const timeLeft = FINAL_CYCLE_COOLDOWN - timeSinceLastAd;
                const hours = Math.floor(timeLeft / (60 * 60 * 1000));
                const minutes = Math.floor((timeLeft % (60 * 60 * 1000)) / (60 * 1000));
                document.getElementById('adsStatusText').textContent = `Next day in: ${hours}h ${minutes}m`;
                document.getElementById('adsTimerDisplay').style.background = "rgba(255, 87, 34, 0.3)";
            }
        }
    } else {
        // Still in current cycle
        document.getElementById('adsStatusText').textContent = `${adsInCurrentCycle}/${MAX_ADS_PER_CYCLE}`;
        document.getElementById('adsTimerDisplay').style.background = "rgba(0, 200, 83, 0.3)";
    }
    
    return true;
}

// Helper function to add small timer
function addSmallTimer(text) {
    let timerElement = document.getElementById('smallTimer');
    if (!timerElement) {
        timerElement = document.createElement('span');
        timerElement.id = 'smallTimer';
        timerElement.className = 'small-timer';
        document.getElementById('adsStatusText').parentNode.appendChild(timerElement);
    }
    timerElement.textContent = text;
    timerElement.style.display = 'inline-block';
}

// Helper function to add cycle timer
function addCycleTimer(text) {
    let timerElement = document.getElementById('cycleTimer');
    if (!timerElement) {
        timerElement = document.createElement('span');
        timerElement.id = 'cycleTimer';
        timerElement.className = 'cycle-cooldown-timer';
        document.getElementById('adsStatusText').parentNode.appendChild(timerElement);
    }
    timerElement.textContent = text;
    timerElement.style.display = 'inline-block';
}

// Helper function to remove timers
function removeTimers() {
    const smallTimer = document.getElementById('smallTimer');
    const cycleTimer = document.getElementById('cycleTimer');
    
    if (smallTimer) {
        smallTimer.style.display = 'none';
    }
    if (cycleTimer) {
        cycleTimer.style.display = 'none';
    }
}

// Start ad watching
function startAdWatch() {
    if (isAdInProgress) return;
    
    const now = Date.now();
    
    // Check if current cycle is completed
    if (adsInCurrentCycle >= MAX_ADS_PER_CYCLE) {
        if (currentCycle < TOTAL_CYCLES) {
            // Cycle 1 or 2 completed - check 30 minute cooldown
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd < CYCLE_COOLDOWN) {
                const timeLeft = CYCLE_COOLDOWN - timeSinceLastAd;
                const minutes = Math.ceil(timeLeft / (60 * 1000));
                showSimpleNotification(`Wait ${minutes} minutes for cycle ${currentCycle + 1}`, "error");
                return;
            } else {
                // Move to next cycle
                currentCycle++;
                adsInCurrentCycle = 0;
                cycleStartTime = now;
                lastAdTime = null;
                saveGameData();
                
                showSimpleNotification(`Cycle ${currentCycle} started!`, "info");
                updateAdSystem();
                updateDrawButton();
                return;
            }
        } else {
            // Cycle 3 completed - check 12 hour cooldown
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : FINAL_CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd < FINAL_CYCLE_COOLDOWN) {
                const timeLeft = FINAL_CYCLE_COOLDOWN - timeSinceLastAd;
                const hours = Math.floor(timeLeft / (60 * 60 * 1000));
                const minutes = Math.floor((timeLeft % (60 * 60 * 1000)) / (60 * 1000));
                showSimpleNotification(`Wait ${hours}h ${minutes}m for next day`, "error");
                return;
            } else {
                // Should have been reset by daily reset system
                showSimpleNotification("Please wait for daily reset", "info");
                return;
            }
        }
    }
    
    // Start ad monitoring
    startAdMonitoring();
}

// Start ad monitoring
function startAdMonitoring() {
    isAdInProgress = true;
    adStartTime = Date.now();
    adWatchedSeconds = 0;
    remainingSeconds = AD_DURATION;
    
    // Update UI
    const drawBtn = document.getElementById('drawBtn');
    drawBtn.disabled = true;
    drawBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Opening Ad...';
    
    // Open ad in new tab
    const adUrl = 'https://example.com/your-ad-link'; // YOUR AD URL HERE
    adTab = window.open(adUrl, '_blank');
    
    // Start monitoring timer
    adTimer = setInterval(monitorAdProgress, 1000);
    
    // Show notification
    showSimpleNotification("Ad opened in new tab. Please don't close it until completed.", "info");
    
    // Update button
    updateDrawButton();
}

// Monitor ad progress
function monitorAdProgress() {
    if (!isAdInProgress) return;
    
    const now = Date.now();
    const elapsedSeconds = Math.floor((now - adStartTime) / 1000);
    
    // Calculate watched seconds (max AD_DURATION)
    adWatchedSeconds = Math.min(elapsedSeconds, AD_DURATION);
    remainingSeconds = AD_DURATION - adWatchedSeconds;
    
    // Update button text
    const drawBtn = document.getElementById('drawBtn');
    if (isAdInProgress) {
        drawBtn.innerHTML = `<i class="fas fa-clock"></i> Watching... ${remainingSeconds}s`;
    }
    
    // Check if ad completed
    if (adWatchedSeconds >= AD_DURATION) {
        completeAdWatch();
    }
    
    // Check if tab is closed
    if (adTab && adTab.closed) {
        handleAdInterrupted();
    }
}

// Handle interrupted ad
function handleAdInterrupted() {
    if (!isAdInProgress) return;
    
    clearInterval(adTimer);
    
    // Calculate remaining seconds
    remainingSeconds = AD_DURATION - adWatchedSeconds;
    
    if (remainingSeconds > 0) {
        // Show incomplete ad overlay
        showIncompleteAdOverlay();
    } else {
        // Ad was actually completed
        completeAdWatch();
    }
}

// Show incomplete ad overlay
function showIncompleteAdOverlay() {
    const incompleteOverlay = document.getElementById('incompleteAdOverlay');
    const remainingSecondsElement = document.getElementById('remainingSeconds');
    const watchSecondsElement = document.getElementById('watchSeconds');
    
    remainingSecondsElement.textContent = remainingSeconds;
    watchSecondsElement.textContent = remainingSeconds;
    
    incompleteOverlay.classList.add('active');
    
    // Set up resume button
    document.getElementById('resumeAdBtn').onclick = function() {
        resumeAdWatch();
    };
}

// Resume ad watch
function resumeAdWatch() {
    const incompleteOverlay = document.getElementById('incompleteAdOverlay');
    incompleteOverlay.classList.remove('active');
    
    // Update ad start time to continue from where we left off
    adStartTime = Date.now() - (adWatchedSeconds * 1000);
    isAdInProgress = true;
    
    // Reopen ad tab
    const adUrl = 'https://example.com/your-ad-link'; // YOUR AD URL HERE
    adTab = window.open(adUrl, '_blank');
    
    // Restart monitoring timer
    adTimer = setInterval(monitorAdProgress, 1000);
    
    // Update button
    const drawBtn = document.getElementById('drawBtn');
    drawBtn.disabled = true;
    drawBtn.innerHTML = `<i class="fas fa-clock"></i> Resuming... ${remainingSeconds}s`;
    
    showSimpleNotification("Resuming ad watch...", "info");
}

// Complete ad watch
function completeAdWatch() {
    if (!isAdInProgress) return;
    
    clearInterval(adTimer);
    isAdInProgress = false;
    
    // Update stats
    const now = Date.now();
    
    coins += AD_REWARD;
    totalAdsWatched++;
    todayAdsWatched++;
    adsInCurrentCycle++;
    lastAdTime = now;
    
    // If this is the first ad of the cycle, set cycle start time
    if (adsInCurrentCycle === 1) {
        cycleStartTime = now;
    }
    
    // Check if cycle completed
    if (adsInCurrentCycle >= MAX_ADS_PER_CYCLE) {
        if (currentCycle < TOTAL_CYCLES) {
            showSimpleNotification(`Cycle ${currentCycle} completed! Wait 30 minutes for cycle ${currentCycle + 1}.`, "info");
        } else if (currentCycle >= TOTAL_CYCLES) {
            showSimpleNotification("Cycle 3 completed! Wait 12 hours for next day.", "info");
        }
    }
    
    // Update UI and save
    updateProgress();
    updateAdSystem();
    saveGameData();
    
    // Update draw button
    updateDrawButton();
    
    // Show reward notification
    showSimpleNotification("Ad completed!", "success", AD_REWARD);
    
    // Close incomplete overlay if open
    const incompleteOverlay = document.getElementById('incompleteAdOverlay');
    incompleteOverlay.classList.remove('active');
}

// Update draw button status
function updateDrawButton() {
    const drawBtn = document.getElementById('drawBtn');
    const now = Date.now();
    
    if (isAdInProgress) {
        drawBtn.disabled = true;
        drawBtn.innerHTML = `<i class="fas fa-clock"></i> Watching... ${remainingSeconds}s`;
        return;
    }
    
    // Check if current cycle is completed
    if (adsInCurrentCycle >= MAX_ADS_PER_CYCLE) {
        if (currentCycle < TOTAL_CYCLES) {
            // Cycle 1 or 2 completed - check 30 minute cooldown
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd < CYCLE_COOLDOWN) {
                const timeLeft = CYCLE_COOLDOWN - timeSinceLastAd;
                const minutes = Math.ceil(timeLeft / (60 * 1000));
                drawBtn.disabled = true;
                drawBtn.innerHTML = `<i class="fas fa-clock"></i> Wait ${minutes}m`;
                return;
            } else {
                // Can move to next cycle
                drawBtn.disabled = false;
                drawBtn.innerHTML = `<i class="fas fa-play-circle"></i> Start Cycle ${currentCycle + 1}`;
                return;
            }
        } else {
            // Cycle 3 completed - check 12 hour cooldown
            const timeSinceLastAd = lastAdTime ? now - lastAdTime : FINAL_CYCLE_COOLDOWN + 1;
            
            if (timeSinceLastAd < FINAL_CYCLE_COOLDOWN) {
                const timeLeft = FINAL_CYCLE_COOLDOWN - timeSinceLastAd;
                const hours = Math.floor(timeLeft / (60 * 60 * 1000));
                const minutes = Math.floor((timeLeft % (60 * 60 * 1000)) / (60 * 1000));
                drawBtn.disabled = true;
                drawBtn.innerHTML = `<i class="fas fa-clock"></i> Wait ${hours}h ${minutes}m`;
                return;
            } else {
                // Should be reset by daily reset
                drawBtn.disabled = true;
                drawBtn.innerHTML = `<i class="fas fa-ban"></i> Wait for reset`;
                return;
            }
        }
    }
    
    // Normal state - can watch ads in current cycle
    drawBtn.disabled = false;
    drawBtn.innerHTML = '<i class="fas fa-play-circle"></i> Watch Ad Now';
}

// Update coin progress
function updateProgress() {
    const progressPercent = (coins / maxCoins) * 100;
    const progressBar = document.getElementById('progressBar');
    const progressText = document.getElementById('progressText');
    
    progressBar.style.width = `${progressPercent}%`;
    
    const formattedCoins = coins.toLocaleString();
    const formattedMaxCoins = maxCoins.toLocaleString();
    const formattedKs = ksValue.toLocaleString();
    
    progressText.textContent = `${formattedCoins}/${formattedMaxCoins} (ks ${formattedKs})`;
}

// Date display function
function updateDateDisplay() {
    const now = new Date();
    const dateElement = document.getElementById('currentDate');
    const resetElement = document.getElementById('nextReset');
    
    // Format date
    const options = { weekday: 'short', month: 'short', day: 'numeric' };
    dateElement.textContent = `Today: ${now.toLocaleDateString('en-US', options)}`;
    
    // Calculate next reset time
    const tomorrow = new Date(now);
    tomorrow.setDate(tomorrow.getDate() + 1);
    tomorrow.setHours(0, 0, 0, 0);
    
    const timeUntilReset = tomorrow.getTime() - now.getTime();
    const hours = Math.floor(timeUntilReset / (60 * 60 * 1000));
    const minutes = Math.floor((timeUntilReset % (60 * 60 * 1000)) / (60 * 1000));
    
    resetElement.textContent = `Reset: ${hours.toString().padStart(2, '0')}:${minutes.toString().padStart(2, '0')}`;
}

// Generate days
function generateDays() {
    const daysWrapper = document.getElementById('daysScrollWrapper');
    daysWrapper.innerHTML = '';
    
    const now = Date.now();
    const timeSinceLastClaim = lastClaimTime ? now - lastClaimTime : 24 * 60 * 60 * 1000 + 1;
    
    for (let i = 0; i < totalDays; i++) {
        const dayDiv = document.createElement('div');
        dayDiv.className = 'day';
        dayDiv.setAttribute('data-day', i);
        
        if (claimedDays.includes(i)) {
            dayDiv.className += ' claimed';
            dayDiv.innerHTML = `
                Day ${i + 1}
                <div class="day-value">${dayRewards[i].toLocaleString()}</div>
            `;
            dayDiv.onclick = null;
            dayDiv.style.cursor = 'default';
        } else if (i === currentDayIndex) {
            if (timeSinceLastClaim >= 24 * 60 * 60 * 1000) {
                dayDiv.className += ' today';
                dayDiv.onclick = () => claimDailyReward(i);
                dayDiv.innerHTML = `
                    Day ${i + 1}
                    <div class="day-value">${dayRewards[i].toLocaleString()}</div>
                    <div class="next-claim-timer">CLAIM NOW</div>
                `;
            } else {
                dayDiv.className += ' today';
                dayDiv.onclick = null;
                dayDiv.style.cursor = 'not-allowed';
                
                const remainingTime = 24 * 60 * 60 * 1000 - timeSinceLastClaim;
                const remainingHours = Math.ceil(remainingTime / (60 * 60 * 1000));
                
                dayDiv.innerHTML = `
                    Day ${i + 1}
                    <div class="day-value">${dayRewards[i].toLocaleString()}</div>
                    <div class="next-claim-timer">WAIT ${remainingHours}hr</div>
                `;
            }
        } else {
            dayDiv.className += ' future';
            dayDiv.onclick = null;
            dayDiv.style.cursor = 'not-allowed';
            dayDiv.innerHTML = `
                Day ${i + 1}
                <div class="day-value">${dayRewards[i].toLocaleString()}</div>
            `;
        }
        
        daysWrapper.appendChild(dayDiv);
    }
}

// Claim daily reward
function claimDailyReward(dayIndex) {
    if (dayIndex !== currentDayIndex) {
        showSimpleNotification("Please claim today's reward first!", "error");
        return;
    }
    
    const now = Date.now();
    if (lastClaimTime && (now - lastClaimTime) < 24 * 60 * 60 * 1000) {
        const remainingTime = 24 * 60 * 60 * 1000 - (now - lastClaimTime);
        const remainingHours = Math.ceil(remainingTime / (60 * 60 * 1000));
        showSimpleNotification(`Please wait ${remainingHours} hours before claiming next reward!`, "error");
        return;
    }
    
    const rewardAmount = dayRewards[dayIndex];
    coins += rewardAmount;
    claimedDays.push(dayIndex);
    lastClaimTime = now;
    
    if (currentDayIndex < totalDays - 1) {
        currentDayIndex++;
    } else {
        showSimpleNotification("All daily rewards claimed! System will reset tomorrow.", "info");
    }
    
    updateProgress();
    generateDays();
    updateClaimTimers();
    saveGameData();
    
    showSimpleNotification("Daily Reward Claimed!", "success", rewardAmount);
}

// Update claim timers
function updateClaimTimers() {
    const now = Date.now();
    
    const todayElement = document.querySelector('.day.today');
    if (todayElement && !todayElement.classList.contains('claimed')) {
        const dayIndex = parseInt(todayElement.getAttribute('data-day'));
        
        if (lastClaimTime) {
            const timeSinceLastClaim = now - lastClaimTime;
            const timeUntilNextClaim = 24 * 60 * 60 * 1000 - timeSinceLastClaim;
            
            if (timeUntilNextClaim <= 0) {
                todayElement.innerHTML = `
                    Day ${dayIndex + 1}
                    <div class="day-value">${dayRewards[dayIndex].toLocaleString()}</div>
                    <div class="next-claim-timer">CLAIM NOW</div>
                `;
                todayElement.onclick = () => claimDailyReward(dayIndex);
                todayElement.style.cursor = 'pointer';
            } else {
                const remainingHours = Math.ceil(timeUntilNextClaim / (60 * 60 * 1000));
                todayElement.innerHTML = `
                    Day ${dayIndex + 1}
                    <div class="day-value">${dayRewards[dayIndex].toLocaleString()}</div>
                    <div class="next-claim-timer">WAIT ${remainingHours}hr</div>
                `;
                todayElement.onclick = null;
                todayElement.style.cursor = 'not-allowed';
            }
        } else {
            todayElement.innerHTML = `
                Day ${dayIndex + 1}
                <div class="day-value">${dayRewards[dayIndex].toLocaleString()}</div>
                <div class="next-claim-timer">CLAIM NOW</div>
            `;
            todayElement.onclick = () => claimDailyReward(dayIndex);
            todayElement.style.cursor = 'pointer';
        }
    }
}

// Show simple notification
function showSimpleNotification(message, type = "success", amount = 0) {
    const notification = document.getElementById('simpleNotification');
    const notificationMessage = document.getElementById('notificationMessage');
    const notificationAmount = document.getElementById('notificationAmount');
    
    // Set notification type
    notification.className = 'simple-notification';
    if (type === "success") {
        notification.style.borderLeftColor = "#4CAF50";
        notificationMessage.innerHTML = `<i class="fas fa-check-circle"></i> ${message}`;
    } else if (type === "error") {
        notification.style.borderLeftColor = "#FF5722";
        notificationMessage.innerHTML = `<i class="fas fa-exclamation-circle"></i> ${message}`;
    } else if (type === "info") {
        notification.style.borderLeftColor = "#2196F3";
        notificationMessage.innerHTML = `<i class="fas fa-info-circle"></i> ${message}`;
    }
    
    if (amount > 0) {
        notificationAmount.textContent = `+${amount.toLocaleString()}`;
        notificationAmount.style.display = "inline";
    } else {
        notificationAmount.style.display = "none";
    }
    
    notification.classList.add('show');
    
    setTimeout(() => {
        notification.classList.remove('show');
    }, 2000);
}

// Show redeem options
let redeemOverlay = null;

function showRedeemOptions() {
    if (redeemOverlay) {
        closeRedeemOptions();
        return;
    }
    
    const neededCoins = maxCoins - coins;
    const hasEnoughCoins = coins >= maxCoins;
    
    const optionHtml = `
        <div class="redeem-options-overlay" id="redeemOverlay">
            <div class="redeem-options-modal">
                <div class="redeem-modal-header">
                    <h3><i class="fas fa-gift"></i> Withdraw Your Reward</h3>
                    <p class="redeem-subtitle">1,000,000 Coins = ks ${ksValue.toLocaleString()}</p>
                </div>
                
                <div class="coin-status-container">
                    <div class="coin-amount-display">
                        <div class="current-amount">
                            <span class="amount-label">Current Coins</span>
                            <div class="amount-value">${coins.toLocaleString()}</div>
                        </div>
                        <div class="required-amount">
                            <span class="amount-label">Required Coins</span>
                            <div class="amount-value">${maxCoins.toLocaleString()}</div>
                        </div>
                    </div>
                    
                    <div class="coin-difference ${hasEnoughCoins ? 'enough' : 'not-enough'}">
                        ${hasEnoughCoins ? 
                            `✅ Ready to withdraw ks ${ksValue.toLocaleString()}` : 
                            `🔸 Need ${neededCoins.toLocaleString()} more coins`}
                    </div>
                </div>
                
                <div class="payment-options-container">
                    <h4 class="payment-options-title">Select Payment Method</h4>
                    <div class="payment-options-grid">
                        <div class="payment-option-simple" onclick="selectPaymentMethod('kpay')">
                            <div class="payment-icon-simple">
                                <img src="https://i.postimg.cc/zv3sN91v/blue-L.webp" alt="KPay" onerror="this.onerror=null;this.src='https://cdn-icons-png.flaticon.com/512/349/349221.png'">
                            </div>
                            <div class="payment-name-simple">KPay</div>
                        </div>
                        
                        <div class="payment-option-simple" onclick="selectPaymentMethod('wavepay')">
                            <div class="payment-icon-simple">
                                <img src="https://i.postimg.cc/CLs1d8yg/Rdefault.png" alt="WavePay" onerror="this.onerror=null;this.src='https://cdn-icons-png.flaticon.com/512/349/349228.png'">
                            </div>
                            <div class="payment-name-simple">WavePay</div>
                        </div>
                    </div>
                </div>
                
                <div class="selected-payment-details" id="paymentDetails">
                    <div class="selected-method-header">
                        <button class="back-button" onclick="goBackToPaymentOptions()">
                            <i class="fas fa-arrow-left"></i>
                        </button>
                        <div class="selected-method-title">
                            <img src="" alt="" class="method-icon" id="selectedMethodIcon">
                            <span class="method-name" id="selectedMethodName"></span>
                        </div>
                        <span class="amount-display">ks ${ksValue.toLocaleString()}</span>
                    </div>
                    
                    <div class="input-group">
                        <label for="accountInput">Account Number / Phone</label>
                        <input type="text" id="accountInput" placeholder="Enter your account number">
                    </div>
                    
                    <div class="input-group">
                        <label for="nameInput">Account Holder Name</label>
                        <input type="text" id="nameInput" placeholder="Enter account holder name">
                    </div>
                    
                    <div class="withdraw-note">
                        <i class="fas fa-info-circle"></i>
                        <p>Withdrawal processed within 24 hours. 1M coins = ks ${ksValue.toLocaleString()}</p>
                    </div>
                </div>
                
                <div class="redeem-modal-actions">
                    <button class="modal-btn cancel-btn" onclick="closeRedeemOptions()">
                        <i class="fas fa-times"></i> Cancel
                    </button>
                    <button class="modal-btn confirm-btn" id="confirmWithdrawBtn" onclick="processWithdrawal()" ${!hasEnoughCoins ? 'disabled' : ''}>
                        <i class="fas fa-paper-plane"></i> ${hasEnoughCoins ? 'Confirm' : 'Need More Coins'}
                    </button>
                </div>
            </div>
        </div>
    `;
    
    document.body.insertAdjacentHTML('beforeend', optionHtml);
    
    redeemOverlay = document.getElementById('redeemOverlay');
    const paymentDetails = document.getElementById('paymentDetails');
    const confirmBtn = document.getElementById('confirmWithdrawBtn');
    
    paymentDetails.style.display = 'none';
    confirmBtn.style.display = 'none';
    
    setTimeout(() => {
        redeemOverlay.classList.add('active');
    }, 10);
}

// 결제 수단 선택
function selectPaymentMethod(method) {
    const paymentOptionsContainer = document.querySelector('.payment-options-container');
    const paymentDetails = document.getElementById('paymentDetails');
    const confirmBtn = document.getElementById('confirmWithdrawBtn');
    const selectedMethodName = document.getElementById('selectedMethodName');
    const selectedMethodIcon = document.getElementById('selectedMethodIcon');
    const coinStatusContainer = document.querySelector('.coin-status-container');
    
    // 선택된 결제 방법 설정
    if (method === 'kpay') {
        selectedMethodName.textContent = 'KPay';
        selectedMethodIcon.src = 'https://i.postimg.cc/zv3sN91v/blue-L.webp';
        selectedMethodIcon.alt = 'KPay';
    } else if (method === 'wavepay') {
        selectedMethodName.textContent = 'WavePay';
        selectedMethodIcon.src = 'https://i.postimg.cc/CLs1d8yg/Rdefault.png';
        selectedMethodIcon.alt = 'WavePay';
    }
    
    // 이미지 로드 실패 시 대체 이미지 설정
    selectedMethodIcon.onerror = function() {
        if (method === 'kpay') {
            this.src = 'https://cdn-icons-png.flaticon.com/512/349/349221.png';
        } else if (method === 'wavepay') {
            this.src = 'https://cdn-icons-png.flaticon.com/512/349/349228.png';
        }
    };
    
    // 현재 화면 숨기기
    coinStatusContainer.style.opacity = '0';
    paymentOptionsContainer.style.opacity = '0';
    
    setTimeout(() => {
        coinStatusContainer.style.display = 'none';
        paymentOptionsContainer.style.display = 'none';
        
        // 결제 세부 정보 표시
        paymentDetails.style.display = 'block';
        confirmBtn.style.display = 'flex';
        
        setTimeout(() => {
            paymentDetails.classList.add('active');
        }, 10);
    }, 200);
    
    // 코인 충분한지 확인
    const hasEnoughCoins = coins >= maxCoins;
    if (hasEnoughCoins) {
        confirmBtn.disabled = false;
        confirmBtn.innerHTML = '<i class="fas fa-paper-plane"></i> Confirm';
    } else {
        confirmBtn.disabled = true;
        confirmBtn.innerHTML = '<i class="fas fa-paper-plane"></i> Need More Coins';
    }
}

// 뒤로가기
function goBackToPaymentOptions() {
    const paymentOptionsContainer = document.querySelector('.payment-options-container');
    const paymentDetails = document.getElementById('paymentDetails');
    const confirmBtn = document.getElementById('confirmWithdrawBtn');
    const coinStatusContainer = document.querySelector('.coin-status-container');
    
    // 현재 화면 숨기기
    paymentDetails.classList.remove('active');
    
    setTimeout(() => {
        paymentDetails.style.display = 'none';
        confirmBtn.style.display = 'none';
        
        // 이전 화면 표시
        coinStatusContainer.style.display = 'block';
        paymentOptionsContainer.style.display = 'block';
        
        setTimeout(() => {
            coinStatusContainer.style.opacity = '1';
            paymentOptionsContainer.style.opacity = '1';
        }, 10);
    }, 200);
}

// 출금 처리
function processWithdrawal() {
    if (coins < maxCoins) {
        const needed = maxCoins - coins;
        showSimpleNotification(`You need ${needed.toLocaleString()} more coins to withdraw ks ${ksValue.toLocaleString()}!`, "error");
        return;
    }
    
    const accountInput = document.getElementById('accountInput');
    const nameInput = document.getElementById('nameInput');
    
    if (!accountInput.value.trim()) {
        showSimpleNotification('Please enter your account number!', 'error');
        accountInput.focus();
        return;
    }
    
    if (!nameInput.value.trim()) {
        showSimpleNotification('Please enter account holder name!', 'error');
        nameInput.focus();
        return;
    }
    
    showSimpleNotification(`Withdrawal request submitted! ks ${ksValue.toLocaleString()} will be processed within 24 hours.`, "success");
    
    coins = 0;
    updateProgress();
    saveGameData();
    
    closeRedeemOptions();
    
    setTimeout(() => {
        showSimpleNotification(`New target set! Collect 1,000,000 coins to withdraw ks ${ksValue.toLocaleString()} again!`, "info");
    }, 1000);
}

// 옵션 창 닫기
function closeRedeemOptions() {
    if (!redeemOverlay) return;
    
    redeemOverlay.classList.remove('active');
    
    setTimeout(() => {
        if (redeemOverlay && redeemOverlay.parentNode) {
            redeemOverlay.parentNode.removeChild(redeemOverlay);
        }
        redeemOverlay = null;
    }, 200);
}

// Developer test functions
function testDailyReset() {
    // Simulate next day
    const now = new Date();
    const yesterday = new Date(now);
    yesterday.setDate(yesterday.getDate() - 1);
    
    lastResetDate = yesterday.toDateString();
    todayAdsWatched = 50;
    currentCycle = 2;
    adsInCurrentCycle = 30;
    
    console.log("Before reset:");
    console.log("- Last reset date:", lastResetDate);
    console.log("- Today's ads:", todayAdsWatched);
    console.log("- Current cycle:", currentCycle);
    console.log("- Ads in cycle:", adsInCurrentCycle);
    
    // Trigger reset
    checkDailyReset();
    
    console.log("After reset:");
    console.log("- Last reset date:", lastResetDate);
    console.log("- Today's ads:", todayAdsWatched);
    console.log("- Current cycle:", currentCycle);
    console.log("- Ads in cycle:", adsInCurrentCycle);
}

function simulateAdWatch(count) {
    // Simulate watching ads
    for(let i = 0; i < count; i++) {
        coins += AD_REWARD;
        totalAdsWatched++;
        todayAdsWatched++;
        adsInCurrentCycle++;
    }
    
    console.log(`Simulated ${count} ads watched`);
    console.log("- Coins:", coins);
    console.log("- Total ads:", totalAdsWatched);
    console.log("- Today's ads:", todayAdsWatched);
    console.log("- Ads in cycle:", adsInCurrentCycle);
    
    updateProgress();
    updateAdSystem();
    saveGameData();
}

function resetForTesting() {
    // Reset for testing
    todayAdsWatched = 0;
    currentCycle = 1;
    adsInCurrentCycle = 0;
    lastAdTime = null;
    cycleStartTime = Date.now();
    
    const now = new Date();
    lastResetDate = now.toDateString();
    
    console.log("Reset complete for testing");
    updateAdSystem();
    saveGameData();
}

// 모바일 최적화
document.addEventListener('touchstart', function() {}, {passive: true});

// Start update intervals
setInterval(updateDrawButton, 1000);
setInterval(updateClaimTimers, 60 * 1000);
setInterval(checkDailyReset, 60 * 1000);
setInterval(updateDateDisplay, 60000); // Update time every minute
setInterval(updateAdSystem, 1000); // Update ad system every second

// Clean up
window.addEventListener('beforeunload', function() {
    closeRedeemOptions();
});
</script>
</body>
</html>
