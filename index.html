<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Gerador de QR Code</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/qrcodejs/qrcode.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f9fa;
        }
        .container {
            background: #fff;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        #qr-code {
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
    </style>
</head>
<body>
    <div class="container mt-5">
        <h3 class="mb-4 text-center">Gerador de QR Code</h3>
        <form id="form-qr">
            <div class="mb-3">
                <label for="qr-type" class="form-label">Tipo de QR Code:</label>
                <select id="qr-type" name="qr-type" class="form-select" required>
                    <option value="" disabled selected>Selecione um tipo</option>
                    <option value="text">Texto</option>
                    <option value="phone">Número de Telefone</option>
                    <option value="email">E-mail</option>
                    <option value="url">Link de Site</option>
                    <option value="whatsapp">Link de WhatsApp</option>
                </select>
            </div>
            <div class="mb-3">
                <label for="qr-data" class="form-label">Conteúdo do QR Code:</label>
                <input type="text" id="qr-data" name="qr-data" class="form-control" placeholder="Digite o conteúdo" required>
            </div>
            <div class="mb-3">
                <label for="caption" class="form-label">Legenda (opcional):</label>
                <input type="text" id="caption" name="caption" class="form-control" placeholder="Digite a legenda">
            </div>
            <div class="row mb-3">
                <div class="col-md-4">
                    <label for="qr-size" class="form-label">Tamanho:</label>
                    <input type="range" id="qr-size" min="100" max="400" value="200" class="form-range">
                </div>
                <div class="col-md-4">
                    <label for="qr-color" class="form-label">Cor do QR Code:</label>
                    <input type="color" id="qr-color" value="#000000" class="form-control form-control-color">
                </div>
                <div class="col-md-4">
                    <label for="bg-color" class="form-label">Cor do Fundo:</label>
                    <input type="color" id="bg-color" value="#ffffff" class="form-control form-control-color">
                </div>
            </div>
            <button type="submit" class="btn btn-primary w-100">Gerar QR Code</button>
        </form>
    </div>

    <div class="modal fade" id="qrModal" tabindex="-1" aria-labelledby="qrModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-dialog-centered">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">QR Code Gerado</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body text-center">
                    <div id="qr-code"></div>
                    <p id="qr-caption" class="mt-2"></p>
                    <button class="btn btn-success mt-3" onclick="saveQrCode()">Salvar</button>
                    <button class="btn btn-secondary mt-3" onclick="printQrCode()">Imprimir</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        function saveQrCode() {
            var qrCanvas = document.querySelector('#qr-code canvas');
            if (qrCanvas) {
                
                var link = document.createElement('a');
                link.href = qrCanvas.toDataURL("image/png");
                link.download = 'codGer/qrcode.png';
                link.click();
                
                var qrData = qrCanvas.toDataURL("image/png");
                fetch('save_qrcode.php', {
                    method: 'POST',
                    body: JSON.stringify({ image: qrData }),
                    headers: { 'Content-Type': 'application/json' }
                })
                .then(response => response.json())
                .then(data => {
                    if (data.success) {
                        alert("QR Code salvo com sucesso na pasta codGer!");
                    } else {
                        alert("Erro ao salvar o QR Code.");
                    }
                })
                .catch(error => console.error('Erro:', error));
            } else {
                alert("Gere um QR Code primeiro!");
            }
        }

        function printQrCode() {
            var qrCanvas = document.querySelector('#qr-code canvas');
            if (qrCanvas) {
                var printWindow = window.open('', '_blank');
                printWindow.document.write('<html><head><title>Imprimir QR Code</title></head><body>');
                printWindow.document.write('<img src="' + qrCanvas.toDataURL() + '"/>');
                printWindow.document.write('</body></html>');
                printWindow.document.close();
                printWindow.print();
            } else {
                alert("Gere um QR Code primeiro!");
            }
        }

        document.getElementById('form-qr').addEventListener('submit', function(event) {
            event.preventDefault();
            
            var qrType = document.getElementById('qr-type').value;
            var qrData = document.getElementById('qr-data').value;
            var captionText = document.getElementById('caption').value;
            var qrSize = document.getElementById('qr-size').value;
            var qrColor = document.getElementById('qr-color').value;
            var bgColor = document.getElementById('bg-color').value;

            if (qrType === 'whatsapp') {
                qrData = 'https://api.whatsapp.com/send?phone=' + qrData;
            } else if (qrType === 'phone') {
                qrData = 'tel:' + qrData;
            } else if (qrType === 'email') {
                qrData = 'mailto:' + qrData;
            } else if (qrType === 'url' && !qrData.startsWith('http://') && !qrData.startsWith('https://')) {
                qrData = 'https://' + qrData;
            }

            document.getElementById('qr-code').innerHTML = '';
            new QRCode(document.getElementById('qr-code'), {
                text: qrData,
                width: parseInt(qrSize),
                height: parseInt(qrSize),
                colorDark: qrColor,
                colorLight: bgColor,
                correctLevel: QRCode.CorrectLevel.H
            });
            
            document.getElementById('qr-caption').innerText = captionText;
            var qrModal = new bootstrap.Modal(document.getElementById('qrModal'));
            qrModal.show();
        });
    </script>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
