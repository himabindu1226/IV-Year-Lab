import javax.crypto.Cipher;
import javax.crypto.KeyGenerator;
import javax.crypto.SecretKey;
import javax.swing.JOptionPane;
public class RC4 {

	public static void main(String[] args)  throws Exception{
		// TODO Auto-generated method stub
		KeyGenerator kg = KeyGenerator.getInstance("Blowfish");
		SecretKey secretkey = kg.generateKey();
		Cipher cipher = Cipher.getInstance("Blowfish");
		cipher.init(Cipher.ENCRYPT_MODE, secretkey);
		String inputtext = "Hello World";
		byte[] encrypted= cipher.doFinal(inputtext.getBytes());
		cipher.init(cipher.DECRYPT_MODE,secretkey);
		byte[] decrypted = cipher.doFinal(encrypted);
		System.out.println("Original String " + inputtext);
		System.out.println("Encrypted text" + new String(encrypted));
		System.out.println("Decrypted text" + new String(decrypted));
		
	}

}