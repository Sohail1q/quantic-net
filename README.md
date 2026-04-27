[quantic-logo.html](https://github.com/user-attachments/files/27119080/quantic-logo.html)
<!DOCTYPE html>
<html>
<body style="font-family: Arial; text-align: center; padding-top: 100px; background-color: #f4f4f4;">
    <div style="background: white; display: inline-block; padding: 40px; border-radius: 20px; shadow: 0px 4px 10px rgba(0,0,0,0.1);">
        <img src="https://i.postimg.cc/TwRjTt0w/Logo-removebg-preview.png" width="100" style="margin-bottom: 20px;"><br>
        <h2 style="color: #333;">Quantic Net Admin</h2>
        <p style="color: #666;">Click below to push the logo to your MetaMask wallet.</p>
        <button id="addLogo" style="background-color: #007bff; color: white; border: none; padding: 15px 30px; font-size: 18px; border-radius: 10px; cursor: pointer; transition: 0.3s;">
            Activate Quantic Logo
        </button>
    </div>

    <script>
        document.getElementById('addLogo').addEventListener('click', async () => {
            if (window.ethereum) {
                try {
                    await window.ethereum.request({
                        method: 'wallet_watchAsset',
                        params: {
                            type: 'ERC20',
                            options: {
                                address: '0x0000000000000000000000000000000000000000',
                                symbol: 'QNT',
                                decimals: 18,
                                image: 'https://i.postimg.cc/TwRjTt0w/Logo-removebg-preview.png',
                            },
                        },
                    });
                } catch (error) {
                    console.error(error);
                    alert("Error: Make sure your PowerShell Geth is running!");
                }
            } else {
                alert("MetaMask not detected!");
            }
        });
    </script>
</body>
</html>
