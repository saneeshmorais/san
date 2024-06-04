# sanfunction sendEmailReport() {
  const sheet = SpreadsheetApp.openById('YOUR_SHEET_ID').getSheetByName('Form Responses');
  const data = sheet.getDataRange().getValues();
  const lastRow = data[data.length - 1];
  const emailAddress = 'saneeshmorais@gmail.com';
  const subject = `AI Analysis for ${lastRow[0]} (${lastRow[1]})`;
  const message = `
    Here is the AI analysis for your token project submission:
    Token Name: ${lastRow[0]}
    Token Symbol: ${lastRow[1]}
    Website: ${lastRow[2]}
    Team Background: ${lastRow[3]}
    Whitepaper Quality: ${lastRow[4]}
    Tokenomics: ${lastRow[5]}
    Technology: ${lastRow[6]}
    Community and Marketing: ${lastRow[7]}
    Roadmap and Milestones: ${lastRow[8]}
    DeFi Focus: ${lastRow[9]}
    NFTs Focus: ${lastRow[10]}
    Gaming Focus: ${lastRow[11]}
    Other Focus: ${lastRow[12]}
    Additional Information: ${lastRow[13]}
    AI Analysis:
    ${lastRow[14]}
  `;
  MailApp.sendEmail(emailAddress, subject, message);
}
